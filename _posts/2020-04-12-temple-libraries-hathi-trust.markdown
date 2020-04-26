---
layout: post
title:  "Learning to HathiTrust csvkit"
date:   2020-04-12 22:38:37 -0400
categories: libraries
---

With the closing of Temple University's physical libraries due to covid-19, and thus the loss of access to our physical collections, library staff have been scrambling to get as much additional content online as possible. One avenue, among many, we have gone down is taking advantage of the HathiTrust [Emergency Temporary Access Service](https://www.hathitrust.org/covid-19-response) (ETAS). HathiTrust offers "a collection of millions of titles digitized from libraries around the world." The copyright restricted content, which is usually unavailable, has been made temporarily available for partner institutions via a digital controlled lending program. We sent Hathi a listing of our physical holdings, which they processed to calculate an overlap report used to determine which items in their collection our users should have access to, and how many digital "copies" of each item would available. They also sent the report back to us to use for our own purposes.

The rest of this blog post will detail the process we went through to understand that data and massage it into shape so we could include it in our ETL process that populates our library catalog, with the end goal of linking from catalog records to the HathiTrust record page where our users can access the digitized copy.

This blog post is also about the amazing set of unix-like tools provided by [csvkit](https://csvkit.readthedocs.io/en/latest/), because I used them almost exclusively to do this work. It was my first time using these tools, and they were perfect for the job and well documented, so they deserve some praise, which they'll get below.

Also, huge shout out to [Frances Webb's blog post](http://blogs.cornell.edu/discoveryandaccess/2020/04/01/adding-hathitrust-emergency-access-links/) on how Cornell worked with the Hathi overlap report to get links into their catalog, as it helped me skip a few steps in understanding the shape of data, and some pitfalls to avoid.

------

## Understanding the data

While I was certainly aware of HathiTrust and their digitized collections before this, I had never dug into the details of how they model their data, what an overlap report would provide, etc. Their [data documentation](https://www.hathitrust.org/data) was helpful, but I needed a bit more hands on digging in our data to really understand it. Since our ultimate goal was links from our catalog, I started with the overlap report which references items in our collections.

### The overlap report

The overlap file provided by Hathi is a five column TSV file, with columns:

* oclc : the OCLC number
* local_id : the item ID of the physical item held by Temple
* item_type : One of three values - mono(graph), multi(part?), or serial
* access: allow, deny or blank
* rights : many different values, none of which are important for our use case.

The file is about 100Mb, so not enormous, but big enough that some process were a bit slow. There wasn't any documentation of the overlap file that I know of, but I was able to infer some stuff from browsing the data a bit, and from looking at the hathi data documentionn.

During the ETAS, we will have access to all of the items with either `allow` or `deny` in the access column. If the access column is empty, it means Hathi does not have a copy of it, so there is nothing to link to, so we can effectively ignore those.

Since I need to filter out rows by value, I decided to use [`csvgrep`](https://csvkit.readthedocs.io/en/latest/scripts/csvgrep.html), which is a lot like unix grep, except it allows you to focus on the data in particular columns of a line. Without it I'd probably be piping `grep` outputs to Cthulhu-level-terrible `awk` commands that I'd almost certainly be ashamed to share with the world.

I also decided to to split the data by `item_type`, as I wondered if monographs and multi-part or serials might require a different approaches when mapping from local identifiers to those held by Hathi. Also, having some smaller files to work with would almost certainly mean that the processing, and hence feedback on my assumptions, would be quicker.

My command looked something like

```bash
csvgrep -t -c 3 -m mono overlap_20200316_temple.tsv | csvgrep -c -4 -r ".+" > ht_overlap_mono.csv
```

Breaking that down:

* `csvgrep -t -c 3 -m mono`
  * `-t`: indicates it is tab delimited instead of comma delimited data
  * `-c 3`: indicates which column we should search in (item_type)
  * `-m mono`: indicates the search term to use in the selected columns
* `| csvgrep -c -4 -r ".+"` : we pipe it to another csvgrep process for more refinement
  * `-c 4` : column 4 (access) this time
  * `-r “.+”`: regex search that requires at least one character. Since a lack of value indicates that HT does not have the item, we want to filter out empty columns.

This outputs a csv file that only includes the monographs we are going to have access to through the ETAS program, in a ~30MB file with 770,077 lines.

Then I did the same for multipart and serials:

```bash
cat overlap_20200316_temple.tsv | csvgrep -t -c 3 -m multi | csvgrep -c -4 -r ".+"
```

```bash
cat overlap_20200316_temple.tsv | csvgrep -t -c 3 -m mono | csvgrep -c -4 -r ".+"
```

Now, with some more consistent data to work with, I needed to understand a bit more about what was in the data. Poking through the files with my text editor gave me a bit of a sense, but I wanted a higher level view. I decided to try `csvstat` on each output file to ensure, to see if it would help.

```bash
csvstat  ht_overlap_mono.csv


  1. "oclc"

    Type of data:          Number
    Contains null values:  False
    Unique values:         637894
    Smallest value:        17
    Largest value:         1,019,844,429
    Sum:                   20,814,034,834,803
    Mean:                  27,028,546.319
    Median:                5,750,865.5
    StDev:                 77,658,357.791
    Most common values:    1,175,417 (24x)
                           1,199,723 (20x)
                           250,896 (20x)
                           260,205 (18x)
                           259,219 (16x)

  2. "local_id"

    Type of data:          Number
    Contains null values:  False
    Unique values:         764783
    Smallest value:        23,237,130,010,003,811
    Largest value:         23,427,799,980,003,811
    Sum:                   17,932,810,712,974,114,759,636
    Mean:                  23,287,066,098,637,166.669
    Median:                23,286,117,055,003,811
    StDev:                 29,532,593,582,807.78
    Most common values:    23,318,950,640,003,811 (3x)
                           23,308,001,580,003,811 (3x)
                           23,316,100,060,003,811 (3x)
                           23,323,166,490,003,811 (3x)
                           23,308,952,980,003,811 (3x)

  3. "item_type"

    Type of data:          Text
    Contains null values:  False
    Unique values:         1
    Longest value:         4 characters
    Most common values:    mono (770076x)

  4. "access"

    Type of data:          Text
    Contains null values:  False
    Unique values:         2
    Longest value:         5 characters
    Most common values:    deny (688662x)
                           allow (81414x)

  5. "rights"

    Type of data:          Text
    Contains null values:  False
    Unique values:         21
    Longest value:         15 characters
    Most common values:    ic (660454x)
                           pd (61592x)
                           und (27309x)
                           pdus (18164x)
                           ic-world (854x)
```

`csvstat` outputs a lot more analysis than I expected (and was a bit noisy with our numberic identifiers), but there are some particularly useful items in there, specifically the:

* reports for item_type, access, and rights report that they have no null values, indicating we have removed the rows for which Hathi does not have a copy.
* unique values for access, show us that the only two values present are allow and deny. The ETAS means we get access to deny as well as access, so that's exactly what we were looking for.

Two pieces of data that I initially missed, but would have been useful to consider at the time were the "number of unique values" and the "most common values" for `oclc` and `local_id`. In my initial mental model,  the `oclc` numbers and our `local_id`s were unique per row, but the report values

* oclc
  * number of unique values: 637,894
  * most common values: 1175417 (24)
* local_id
  * number of unique values: 764,783
  * most common values: 23318950640003811 (3x)
  
show a different story. Much less than the 770,076 rows of data. Knowing that would have helped to correct my mental model, but I initially just glazed over it. So, `csvstat` provided lots of assistance, even if I wasn't yet ready to receive it.

Now that we have these three files, representing the physical items in our collection that Hathi knows we have and the OCLC number for each item, we can move on to figuring how to map those item records to Hathi URLs that will allow our users to access the digitized items.

------

## Connecting to HathiTrust Records

So, while we could use the oclc number we already have with the [Hathi bibligraphic api](https://www.hathitrust.org/bib_api) to dynamically look up the Hathi Record URL when our catalog display an item from the processed overlap report, that would mean we don't know which items were available until page load, meaning it would not reflect in our existing affordances for "Online Resources" like facets. To integrate with existing affordances, we need to get the data into the Solr collection that powers our catalog.

Based on the [Hathi docs on linking](https://www.hathitrust.org/automatic_login), we want to link to Record pages, as they provide the most context for our users. It seemed to me the best way to identify the needed record numbers was to use "[Hathifiles](https://www.hathitrust.org/hathifiles)", which are "tab-delimited text files that describe every item in the HathiTrust collection." These files include the OCLC number and record id for each item, which seemed to provide a path to link our overalp report to the records.

Specifically, I downloaded [hathi_full_20200201.txt.gz](https://www.hathitrust.org/filebrowser/download/291461) and [hathi_field_list.txt](https://www.hathitrust.org/filebrowser/download/269539). I want the final file to have headers, so the first thing I did was save `hathi_fieild_list.txt` to a new file called `hathi_with_headers` and then append the full record listing into that. To avoid unzipping the full record file first, I used gzcat

```gzcat hathi_full_20200201.txt.gz >> hathi_with_headers```

This file is about 4.3GB, so totally unwieldy to work with, so first thing I’m going to want to do is shrink it using some filtering. As this is another tsv file, so csvkit still gonna be the right tool for the job.

Since I previously split up our overlap files by type (mono, serial, and multi),  I did the same for the full record list, hoping to get it down to a set of manageable chunks to work with. What’s odd though, is that Hathi's full record file uses a different set of terms of those types. The values are instead BK, SE, MP, which I interpret as Book, Serial, and MultiPart.

So, to get just the books from the hathi full record list I run

```bash
cat hathi_with_header | csvgrep -t -c 20 -m BK -z=1310720 > hathi_with_header_books.csv 
```

Breaking that down:

* `-t` : tab delimted
* `-c 20`: search in column 20, which in this case is bib_fmt
* `-m BK`: use BK as the search term in the bib_fmt column
* `-z=1310720`: csvkit has a default field size limit of 131072 characters, which apparently is too small for some Hathi records rows (I'm guessing the ones with unicode titles?). I multiplied the default by 10, just to be safe.

So, now filtered down to just the monographs, the file has shrunk to...3.4GB. :( NEEDS MORE FILTERING.

Since we've already filtered rows we don't need, the next logical step is to filter columns we don't need. I only really cared about a few fields from the Hathi Records.

* htid (column 1)
* bib_key_id (column 4)
* oclc_num (column 8)

This time I reached for [csvcut](https://csvkit.readthedocs.io/en/latest/scripts/csvcut.html), which:
>filters and truncates CSV files. Like the Unix “cut” command, but for tabular data.

A quick `csvcut -z 1310720 -c 1,4,8 hathi_with_header_books.csv`, and we have selected just those columns, which bring us down to a respectable 400M. A 85% reduction in size is pretty good for a one liner.

So...what to do now. We have:

* a list of all of our overlap items with:
  * oclc_num
  * mms_id
  * A few more fields that no longer seem as relevant
* A list of all the books from Hathi with:
  * htid: the hathi trust ID
  * bib_key_id: another identifier used by HT items
  * oclc_number

What we really want to get to is a list of all of the books from our overlap report with the Hathi Trust identifiers so we can link directly to them from our library catalog. The piece of data connecting these two lists of data is the oclc_num. If this were a SQL database we would join these two tables on oclc_num.

Luckily, once again, csvkit has your back. `csvjoin` was built for exactly this kind of problem.

So I ran:

```bash
csvjoin -y 0 -c 1,3 ht_overlap_mono.csv hathi_with_header_books_minimal_columns.csv \
  > joined_overlap_hathi.csv
```

Breaking that down:

* `-y 0`: "Limit CSV dialect sniffing to the specified number of bytes." I think this helped with the bigger file? I could be wrong.
* `-c 1,3`: in csvjoin, the -c flag indicates the columns to join on respective to the files passed as the positional arguments. So in this case, use column 1 from `ht_overlap_mono.csv` and column 3 from `hathi_with_header_books_minimal_columns.csv`

Now, I'll be honest, `csvjoin` with big old files like this is not performant. It took probably 30 minutes for this to run on my five year old mac book pro. Definitely could have been faster, but the results were exactly what *I thought* I wanted; a new file with the headers
```oclc,local_id,item_type,access,rights,htid,ht_bib_key```
and a limited set of hathis IDs related to items in our overlap report.

## Mistaken Mental Model

So, just to do some basic smoke testing, I wanted to make sure the number of rows in `ht_overlap_mono.csv` was equal to the number of rows in the new `joined_overlap_hathi.csv`. 

```bash
wc -l ht_overlap_mono.csv
77077

wc -l
11575650

wc -l joined_overlap_hathi.csv
1045708
```

Uhh, wat?

How could a join on unique ids hand have more rows than the number of ids in the smallest dataset? Running csvstat on the join file produced some interesting results that made it quickly obvious:

```text
## I removed some fields to reduce noise.
  1. "oclc"

  Type of data:          Number
  Unique values:         614893
  Most common values:    1,175,417 (144x) <------- my emphasis
                         265,046 (90x)
                         711,022 (90x)
                         217,758 (84x)
                         259,219 (80x)

  2. "local_id"

  Type of data:          Number
  Unique values:         738527
  Most common values:    23,304,874,110,003,811 (26x) <------- my emphasis
                         23,251,931,190,003,811 (26x)
                         23,322,074,210,003,811 (22x)
                         23,280,098,830,003,811 (22x)
                         23,293,578,800,003,811 (20x)

  3. "htid"

  Type of data:          Text
  Contains null values:  False
  Unique values:         843988
  Longest value:         25 characters
  Most common values:    mdp.39015072135042 (24x) <------- my emphasis
                         mdp.39015000687783 (24x)
                         mdp.39015005304780 (24x)
                         mdp.39015066017032 (24x)
                         mdp.39015064422515 (24x)

  4. "ht_bib_key"

  Type of data:          Number
  Unique values:         621654
  Most common values:    1,452,934 (144x) <------- my emphasis
                         3,838 (90x)
                         427,209 (84x)
                         1,109,812 (80x)
                         1,274,588 (77x)
```

Lots of identifiers were reused many times. Looking back at the orignal data files, I realized that the Hathi metadata file has many records with the same oclc_num, representing either difeerent digitized copies of the same item, or multiple volumes of the same item. Additionally, the overlap report contained many entries with duplicate oclc numbers, because the report is at the physical item level, letting Hathi know how many copies of something we have so they know how many users to allow access to it.

Luckily, this is a problem that `uniq` was built to solve.

Additionally, in reading a bit more about Hathi's data and the links we'd want to be constructing, I realized that the best ID to use for linking is not the `htid`, which links to an individual instance of an record, often without much context, but the `ht_bib_key` which links to a landing page with all available copies of an item, plus useful metadata.

So, going back to `hathi_with_headers`, to get just the oclc number and ht_bib_key for all rows I ran:

`csvcut -t -c 4,8 -z 1310720 hathi_with_header  > hathi_with_header_all_types_oclc_and_bibkeyid.csv`

and then, to remove lines without either an oclc number or ht_bib_key:

```bash
csvgrep -c 1,2 -r ".+"  hathi_with_header_all_types_oclc_and_bibkeyid.csv > hathi_with_header_all_types_oclc_and_bibkeyid_no_nulls.cs
```

and then finally, used the standard *nix `uniq` command to remove duplicate lines.(Luckily, the Hathi file is already sorted, with rows with the same oclc num being next to each other, which `uniq` requires.)

```bash
cat hathi_with_header_all_types_oclc_and_bibkeyid_no_nulls.csv | uniq > hathi_with_header_all_types_oclc_and_bibkeyid_unique.csv
```

So now we have a file with all of the Hathi items with just an oclc number and a ht_bib_key. Now what we need is an list of oclc numbers to filter it by.

So, going back to our original overalp report, to get a list of items of all types but limit it to just the oclc number we can run:

```bash
csvgrep -t -c -4 -r ".+" overlap_20200316_temple.tsv | csvcut -c 1 > overlap_all.csv
```

But that list contains some repeated oclc numbers that we want to eliminate, so we use `csvsort` to sort the row (not all oclc numbers were in adjacent rows), while retaining the first row as the header.

```bash
cat overlap_all.csv | csvsort | uniq > overlap_all_unique.csv

```

Now we have the second file we need, which is just a big list of oclc numbers. But how to filter the full list by the second?

My first thought was to use `csvjoin` again, but it returned an empty csv file. And reflecting on it, there was nothing to actually "join" in the SQL sense, since one of the csv files was a one column set of id's to be used for the join.

What I really wanted to do was filter the Hathi records csv by the overlap csv. And filtering is exactly what `csvgrep` does. And even more impressively, reading the docs, it turns out csvgrep implements a `-f` flag which uses the lines of a file as the filter criteria.

So...after all that...🥁🥁🥁

```bash
csvgrep -c 2 -f overlap_all_unique.csv hathi_with_header_all_types_oclc_and_bibkeyid_unique.csv > hathi_filtered_by_overlap.csv
```

got me the exact set of data I was looking for: the list of OCLC numbers and corresposning ht_bib_keys that Hathi knows that Temple holds. And it comes in at just 12MB. Small enough to quickly grep for oclc numbers while we are indexing records to see what Hathi bib key we want to add.
