---
layout: post
title:  "Gaimidian Graveyard"
date:   2022-12-03 00:00:00 -0400
---

This year, my plan for [NaNoGenMo](https://nanogenmo.github.io/) was to generate random noise that would be detected as words by speech-to-text processing, and use those to write a book. The idea was loosely inspired by [Reverse OCR bot](https://github.com/dariusk/reverseocr), which has always been one of my favorite projects that probes the absurd edges of what it means for a computer to "recognize" human language. 

Having absolutely no previous experience with audio Engineering, I wasn't really sure how to generate sounds that would be vaguely similar to the human voice. But when I came across Andy Baio's [*If Drake Was Born A Piano*](https://waxy.org/2015/12/if_drake_was_born_a_piano/) describing the disconcertingly nearly-human sound of a human voice in a song that has been converted to MIDI, I knew exactly what I wanted to do. 


So, the plan became:
1. Find a freely available mp3 audio book to download
2. Convert the mp3 to MIDI and the back to an mp3, thus creating an audio book with weirdly distorted speech
3. Run the midified-mp3 through OpenAI Whisper, the automated speech-recognition system
4. Hope the output is weird enough to make an interesting   #nanogenmo 

Unfortunately, my first attempts with [my process](#how-i-created-these-on-my-mac) didn't provide very good output from whisper. It was often very low in textual content, or just a lot of repetition. COnsider the first two I tried:

[Librivox recording of Jane Austen's *Emma*](https://ia803406.us.archive.org/20/items/emma_version_5_1002_librivox/emma_01_austen_64kb.mp3)

*Midified Audio*

<audio controls>
  <source 
    src="/words/assets/emma_01_01_austen-roundtripped.mp3" type="audio/mp3">
</audio>

<details>
  <summary>Midified Transcript</summary>
  1
  00:00:00,000 --> 00:00:02,000
  🎶🎶🎶

  2
  00:01:30,000 --> 00:01:35,000
  ...

  3
  00:01:35,000 --> 00:01:40,000
  ...

  4
  00:01:40,000 --> 00:01:45,000
  ...

  5
  00:01:45,000 --> 00:01:50,000
  ...

  6
  00:01:50,000 --> 00:01:55,000
  ...

  7
  00:03:25,000 --> 00:03:32,000
  Mm.

  8
  00:03:32,000 --> 00:03:39,000
  Mm.

  9
  00:03:39,000 --> 00:03:46,000
  Mm.

  10
  00:03:46,000 --> 00:03:53,000
  Mm.

  11
  00:03:53,000 --> 00:04:00,000
  Mm.

  12
  00:04:00,000 --> 00:04:07,000
  Mm.

  13
  00:04:07,000 --> 00:04:17,000
  Mm.

  14
  00:04:17,000 --> 00:04:27,000
  Mm.

  15
  00:04:27,000 --> 00:04:37,000
  Mm.

  16
  00:04:37,000 --> 00:04:47,000
  Mm.

  17
  00:04:47,000 --> 00:04:57,000
  Mm.

  18
  00:04:57,000 --> 00:05:07,000
  Mm.

  19
  00:05:07,000 --> 00:05:17,000
  Mm.

  20
  00:05:17,000 --> 00:05:27,000
  Mm.

  21
  00:05:27,000 --> 00:05:37,000
  Mm.

  22
  00:05:37,000 --> 00:05:47,000
  Mm.

  23
  00:05:47,000 --> 00:05:57,000
  Mm.

  24
  00:05:57,000 --> 00:06:07,000
  Mm.

  25
  00:06:07,000 --> 00:06:17,000
  Mm.

  26
  00:06:17,000 --> 00:06:27,000
  Mm.

  27
  00:06:27,000 --> 00:06:37,000
  Mm.

  28
  00:06:37,000 --> 00:06:47,000
  Mm.

  29
  00:06:47,000 --> 00:06:57,000
  Mm.

  30
  00:06:57,000 --> 00:07:07,000
  Mm.

  31
  00:07:07,000 --> 00:07:17,000
  Mm.

  32
  00:07:17,000 --> 00:07:27,000
  Mm.

  33
  00:07:27,000 --> 00:07:37,000
  Mm.

  34
  00:07:37,000 --> 00:07:47,000
  Mm.

  35
  00:07:47,000 --> 00:07:57,000
  Mm.

  36
  00:07:57,000 --> 00:08:07,000
  Mm.

  37
  00:08:07,000 --> 00:08:17,000
  Mm.

  38
  00:08:17,000 --> 00:08:37,000
  Mm.

  39
  00:08:37,000 --> 00:08:47,000
  Mm.

  40
  00:08:47,000 --> 00:08:57,000
  Mm.

  41
  00:08:57,000 --> 00:09:07,000
  Mm.

  42
  00:09:07,000 --> 00:09:17,000
  Mm.

  43
  00:09:17,000 --> 00:09:27,000
  Mm.

  44
  00:09:27,000 --> 00:09:47,000
  Mm.

  45
  00:09:47,000 --> 00:10:07,000
  Mm.

  46
  00:10:07,000 --> 00:10:27,000
  Mm.

  47
  00:10:27,000 --> 00:10:47,000
  Mm.

  48
  00:10:47,000 --> 00:11:07,000
  Mm.

  49
  00:11:07,000 --> 00:11:27,000
  Mm.

  50
  00:11:27,000 --> 00:11:47,000
  Mm.

  51
  00:11:47,000 --> 00:12:07,000
  Mm.

  52
  00:12:07,000 --> 00:12:27,000
  Mm.

  53
  00:12:27,000 --> 00:12:47,000
  Mm.

  54
  00:12:47,000 --> 00:13:07,000
  Mm.

  55
  00:13:07,000 --> 00:13:27,000
  Mm.

  56
  00:13:27,000 --> 00:13:47,000
  Mm.

  57
  00:13:47,000 --> 00:14:07,000
  Mm.

  58
  00:14:07,000 --> 00:14:27,000
  Mm.

  59
  00:14:27,000 --> 00:14:47,000
  Mm.

  60
  00:14:47,000 --> 00:15:07,000
  Mm.

  61
  00:15:07,000 --> 00:15:27,000
  Mm.

  62
  00:15:27,000 --> 00:15:47,000
  Mm.

  63
  00:15:47,000 --> 00:16:07,000
  Mm.

  64
  00:16:07,000 --> 00:16:27,000
  Mm.

  65
  00:16:27,000 --> 00:16:47,000
  Mm.

  66
  00:16:47,000 --> 00:17:07,000
  Mm.

  67
  00:17:07,000 --> 00:17:27,000
  Mm.

  68
  00:17:27,000 --> 00:17:47,000
  Mm.

  69
  00:17:47,000 --> 00:18:07,000
  Mm.

  70
  00:18:07,000 --> 00:18:27,000
  Mm.

  71
  00:18:27,000 --> 00:18:47,000
  Mm.

  72
  00:18:47,000 --> 00:19:07,000
  Mm.

  73
  00:19:07,000 --> 00:19:27,000
  Mm.

  74
  00:19:27,000 --> 00:19:47,000
  Mm.

  75
  00:19:47,000 --> 00:20:07,000
  Mm.

  76
  00:20:07,000 --> 00:20:27,000
  Mm.

  77
  00:20:27,000 --> 00:20:47,000
  Mm.

  78
  00:20:47,000 --> 00:21:07,000
  Mm.

  79
  00:21:07,000 --> 00:21:27,000
  Mm.

  80
  00:21:27,000 --> 00:21:47,000
  Mm.

</details>

Mmm...pretty boring.


[An excerpt of James Earl Jones reading the Bible](https://d3dqntzfhcgpyw.cloudfront.net/bk/topi/000001/bk_topi_000001_sample.mp3)

<audio controls>
  <source
  src="/words/assets/james-earl-jones-roundtripped.mp3"
  type="audio/mp3"
  >
</audio>

<details>
  <summary> 
    Midified Transcript
  </summary>
  1
  00:04:00,000 --> 00:04:05,000
  .

  2
  00:04:05,000 --> 00:04:10,000
  .

  3
  00:04:10,000 --> 00:04:15,000
  .

  4
  00:04:15,000 --> 00:04:20,000
  .

  5
  00:04:20,000 --> 00:04:25,000
  .

  6
  00:04:55,000 --> 00:04:57,000
  Thank you very much.

</details>
<br>

A fail of nearly Biblical proportions.

<br>

But when I tried [Will Self reading Jorge Luis Borges' *On Exactitude in Science*](https://static.guim.co.uk/audio/kip/books/series/books/1354894458366/9687/gdn.book.121215.tm.Will-Self-Jorge-Luis-Borges-story.mp3), things started looking up. I mean, with a first heard line like 

<audio controls>
  <source 
    src="/words/assets/borges-roundtripped.mp3" type="audio/mp3">
</audio>

<details>
  <summary>Midified Transcript</summary>

  1
  00:00:00,000 --> 00:00:20,180
  The procedure is here…

  2
  00:00:20,180 --> 00:00:31,180
  In the 12th and 15th of next year's time, I'll do a three-pointer.

  3
  00:00:31,180 --> 00:00:36,180
  In this empire, we are top of the three-pointer set.

  4
  00:00:36,180 --> 00:00:42,180
  That's the single spot of my empire.

  5
  00:00:42,180 --> 00:00:47,180
  That's the single spot of my empire.

  6
  00:00:47,180 --> 00:00:52,180
  Hitting the mine was done by a fellow named Haylike.

  7
  00:00:52,180 --> 00:00:54,180
  That's the spot for the three-pointer.

  8
  00:00:54,180 --> 00:00:58,180
  That's the land that I discovered in the past.

  9
  00:00:58,180 --> 00:01:03,180
  That's to be the victims' home in the end.

  10
  00:01:03,180 --> 00:01:11,180
  Of a creative constitution that I found at best if I opened it that day.

  11
  00:01:11,180 --> 00:01:13,680
  GTN 12���

  12
  00:01:13,680 --> 00:01:15,180
  One of the men.

  13
  00:01:15,180 --> 00:01:20,180
  Not without conflict, but they simply did it up,

  14
  00:01:20,180 --> 00:01:24,180
  they went to the bottom.

  15
  00:01:24,180 --> 00:01:28,180
  The dead went to the grave,

  16
  00:01:28,180 --> 00:01:31,180
  but the exit moved for the first time,

  17
  00:01:31,180 --> 00:01:33,180
  and if I am,

  18
  00:01:33,180 --> 00:01:40,180
  but if I am, there is no other way.

  19
  00:01:40,180 --> 00:01:45,180
  The dead went to the grave,

  20
  00:01:45,180 --> 00:01:48,180
  but the exit moved for the first time,

  21
  00:01:48,180 --> 00:01:50,180
  and if I am,

  22
  00:01:50,180 --> 00:02:13,180
  but if I am, there is no other way.

  23
  00:02:13,180 --> 00:02:21,180
  The dead went to the grave,

  24
  00:02:21,180 --> 00:02:26,180
  but the exit moved for the first time,

  25
  00:02:26,180 --> 00:02:28,180
  and if I am,

  26
  00:02:28,180 --> 00:02:36,180
  but if I am, there is no other way.

  27
  00:02:36,180 --> 00:02:44,180
  The dead went to the grave,

  28
  00:02:44,180 --> 00:02:49,180
  but the exit moved for the first time,

  29
  00:02:49,180 --> 00:02:51,180
  and if I am,

  30
  00:02:51,180 --> 00:02:57,180
  but if I am, there is no other way.

  31
  00:02:57,180 --> 00:03:03,180
  The dead went to the grave,

  32
  00:03:03,180 --> 00:03:07,180
  but the exit moved for the first time,

  33
  00:03:07,180 --> 00:03:09,180
  and if I am,

  34
  00:03:09,180 --> 00:03:17,180
  but if I am, there is no other way.

  35
  00:03:17,180 --> 00:03:23,180
  The dead went to the grave,

  36
  00:03:23,180 --> 00:03:27,180
  but the exit moved for the first time,

  37
  00:03:27,180 --> 00:03:29,180
  and if I am,

  38
  00:03:29,180 --> 00:03:36,180
  but if I am, there is no other way.

  39
  00:03:36,180 --> 00:03:41,180
  The dead went to the grave,

  40
  00:03:41,180 --> 00:03:44,180
  but the exit moved for the first time,

  41
  00:03:44,180 --> 00:03:46,180
  and if I am,

  42
  00:03:46,180 --> 00:03:51,180
  but if I am, there is no other way.

  43
  00:03:51,180 --> 00:03:53,180
  I get down on my knees and think

  44
  00:03:53,180 --> 00:03:55,180
  that I can do more than I think.

  45
  00:03:55,180 --> 00:03:56,180
  It won't let me think

  46
  00:03:56,180 --> 00:03:58,180
  that I can do more than I think.

  47
  00:03:58,180 --> 00:04:00,180
  I can do it.

  48
  00:04:00,180 --> 00:04:02,180
  I'm not a fool.

  49
  00:04:02,180 --> 00:04:05,180
  The dead went to the grave,

  50
  00:04:05,180 --> 00:04:09,180
  but the exit moved for the first time,

  51
  00:04:09,180 --> 00:04:11,180
  and if I am,

  52
  00:04:11,180 --> 00:04:16,180
  but if I am, there is no other way.

  53
  00:04:16,180 --> 00:04:19,180
  The dead went to the grave,

  54
  00:04:19,180 --> 00:04:22,180
  but the exit moved for the first time,

  55
  00:04:22,180 --> 00:04:23,180
  and if I am,

  56
  00:04:23,180 --> 00:04:27,180
  but if I am, there is no other way.

  57
  00:04:27,180 --> 00:04:29,180
  I get down on my knees and think

  58
  00:04:29,180 --> 00:04:34,180
  that I can do more than I think.

  59
  00:04:34,180 --> 00:04:36,180
  I can do it.

  60
  00:04:36,180 --> 00:04:38,180
  I'm not a fool.

  61
  00:04:38,180 --> 00:04:41,180
  The dead went to the grave,

  62
  00:04:41,180 --> 00:04:45,180
  but the exit moved for the first time,

  63
  00:04:45,180 --> 00:04:47,180
  and if I am,

  64
  00:04:47,180 --> 00:04:52,180
  but if I am, there is no other way.

  65
  00:04:52,180 --> 00:04:54,180
  I get down on my knees and think

  66
  00:04:54,180 --> 00:04:56,180
  that I can do more than I think.

  67
  00:04:56,180 --> 00:04:57,180
  I can do it.

  68
  00:04:57,180 --> 00:04:59,180
  I'm not a fool.

  69
  00:04:59,180 --> 00:05:01,180
  The dead went to the grave,

  70
  00:05:01,180 --> 00:05:04,180
  but the exit moved for the first time,

  71
  00:05:04,180 --> 00:05:05,180
  and if I am,

  72
  00:05:05,180 --> 00:05:09,180
  but if I am, there is no other way.

  73
  00:05:09,180 --> 00:05:11,180
  I get down on my knees and think

  74
  00:05:11,180 --> 00:05:13,180
  that I can do more than I think.

  75
  00:05:13,180 --> 00:05:14,180
  I can do it.

  76
  00:05:14,180 --> 00:05:15,180
  I'm not a fool.

  77
  00:05:15,180 --> 00:05:17,180
  The dead went to the grave,

  78
  00:05:17,180 --> 00:05:20,180
  but the exit moved for the first time,

  79
  00:05:20,180 --> 00:05:21,180
  and if I am,

  80
  00:05:21,180 --> 00:05:24,180
  but if I am, there is no other way.

  81
  00:05:24,180 --> 00:05:26,180
  I get down on my knees and think

  82
  00:05:26,180 --> 00:05:28,180
  that I can do more than I think.

  83
  00:05:28,180 --> 00:05:30,180
  I can do it.

  84
  00:05:30,180 --> 00:05:32,180
  I'm not a fool.

  85
  00:05:32,180 --> 00:05:34,180
  The dead went to the grave,

  86
  00:05:34,180 --> 00:05:37,180
  but the exit moved for the first time,

  87
  00:05:37,180 --> 00:05:38,180
  and if I am,

  88
  00:05:38,180 --> 00:05:42,180
  but if I am, there is no other way.

  89
  00:05:42,180 --> 00:05:45,180
  I get down on my knees and think

  90
  00:05:45,180 --> 00:05:49,180
  that I can do more than I think.

  91
  00:05:49,180 --> 00:05:51,180
  I'm not a fool,

  92
  00:05:51,180 --> 00:05:53,180
  the dead went to the grave,

  93
  00:05:53,180 --> 00:05:58,180
  It's the end of the world, it's the end of the world.

</details>

That was exactly the kind of output I was hoping for. At this point, I rushed to quick hypothesis: British voices fare better at being midified, and therefore I should try some more.

So, I started with this [youtube playlist of John Cleese reading *The Screwtape Letters*](https://www.youtube.com/playlist?list=PLA8BAC9375345E6C7) which also produced some great output.

<audio controls
  src="/words/assets/screwtape.mp3"
  type="audio/mp3">
</audio>

<details>
<summary> Midified Transcript of pt. 1</summary>
1
00:00:30,000 --> 00:00:34,400
By the time I'm back down on the top of 35th Street,

2
00:00:34,400 --> 00:00:39,280
There's a group of animals there, which are waiting for about a year.

3
00:00:39,280 --> 00:00:43,200
I can't believe they've all been gathered here,

4
00:00:43,200 --> 00:00:47,200
And it feels like they're going to kill me for sure.

5
00:00:47,200 --> 00:00:49,760
I can't believe they're all going to kill me for sure.

6
00:00:49,760 --> 00:00:51,760
I can't believe they're all going to kill me for sure.

7
00:00:51,760 --> 00:00:54,160
I can't believe they're all going to kill me for sure.

8
00:00:54,160 --> 00:01:00,160
By the time I'm back down on the top of 35th Street,

9
00:01:00,160 --> 00:01:06,640
There's a group of animals there, which are waiting for about a year.

10
00:01:06,640 --> 00:01:11,200
I can't believe they're all going to kill me for sure.

11
00:01:11,200 --> 00:01:16,640
I can't believe they're all going to kill me for sure.

12
00:01:16,640 --> 00:01:21,120
I can't believe they're all going to kill me for sure.

13
00:01:21,120 --> 00:01:22,980
I see them in my field

14
00:01:23,020 --> 00:01:25,320
All the three things I've done

15
00:01:25,320 --> 00:01:28,360
All this game's gotta go through the jack

16
00:01:28,380 --> 00:01:32,020
We are the brothers to the 19 and theneh

17
00:01:32,780 --> 00:01:34,600
They'll just sit around with me

18
00:01:34,600 --> 00:01:35,600
With my dress in the neck

19
00:01:35,600 --> 00:01:38,000
Give up the full honor to do the math

20
00:01:38,140 --> 00:01:39,240
I'm going through a year

21
00:01:39,240 --> 00:01:40,760
To be these nice boys

22
00:01:40,760 --> 00:01:42,700
And you're still here

23
00:01:42,760 --> 00:01:45,140
What do the bangers talk about to the baddies

24
00:01:45,140 --> 00:01:46,160
They say saying

25
00:01:46,160 --> 00:01:47,400
Tell you that through life

26
00:01:47,400 --> 00:01:48,940
I've got you

27
00:01:48,940 --> 00:01:52,940
This is where the music gets more access to the heart of a passing town.

28
00:01:52,940 --> 00:01:55,940
That's where the music goes through the speech of what you hear,

29
00:01:55,940 --> 00:01:58,940
with all the things that you have to say.

30
00:01:58,940 --> 00:01:59,940
Hmm.

31
00:02:01,940 --> 00:02:03,940
Number one.

32
00:02:04,940 --> 00:02:06,940
I know the world.

33
00:02:06,940 --> 00:02:09,940
I know what you say about how you want things to be,

34
00:02:09,940 --> 00:02:11,940
how you want things to be better,

35
00:02:11,940 --> 00:02:13,940
and how you want things to be better, too.

36
00:02:13,940 --> 00:02:14,940
Thanks.

37
00:02:14,940 --> 00:02:17,940
But I'm not interested in money.

38
00:02:17,940 --> 00:02:19,940
I'm interested in the art,

39
00:02:19,940 --> 00:02:22,940
the way you try to get a truck.

40
00:02:23,940 --> 00:02:27,940
But I might be better if you're interested in something better than that.

41
00:02:27,940 --> 00:02:30,940
You may be more interested in what you do,

42
00:02:30,940 --> 00:02:32,940
and what you're not.

43
00:02:32,940 --> 00:02:35,940
But if you're good at what you do,

44
00:02:35,940 --> 00:02:37,940
then you can make the world better,

45
00:02:37,940 --> 00:02:42,940
and it might be better to open up your mind after all that you're doing.

46
00:02:42,940 --> 00:02:46,940
Number two.

47
00:02:46,940 --> 00:02:48,940
I know the world.

48
00:02:48,940 --> 00:02:51,940
I know what you say about how you want things to be,

49
00:02:51,940 --> 00:02:54,940
how you want things to be better,

50
00:02:54,940 --> 00:02:57,940
and how you want things to be better, too.

51
00:02:57,940 --> 00:02:59,940
Thanks.

52
00:02:59,940 --> 00:03:02,940
But I'm not interested in money.

53
00:03:02,940 --> 00:03:04,940
I know the world.

54
00:03:04,940 --> 00:03:07,940
I know what you want to do,

55
00:03:07,940 --> 00:03:10,940
and how you want things to be better, too.

56
00:03:10,940 --> 00:03:16,260
Now I may always think it like the mind is not made

57
00:03:16,460 --> 00:03:20,200
and which mind I make means what am I

58
00:03:20,380 --> 00:03:24,800
making and what time or time or time

59
00:03:25,320 --> 00:03:30,900
and sometimes I will lose myself in hate

60
00:03:32,360 --> 00:03:36,680
so I think I am in love with the fall around me

61
00:03:36,680 --> 00:03:40,360
in a man isn't applauded and snubbed

62
00:06:10,360 --> 00:06:13,360
You know what, while we're at it, don't give a damn about it now.

63
00:06:13,360 --> 00:06:16,360
It's just a matter of time.

64
00:06:16,360 --> 00:06:18,360
We're really not that far away yet.

65
00:06:18,360 --> 00:06:21,360
And we'll be taking care of it for the rest of our lives.

66
00:06:21,360 --> 00:06:24,360
And, you know, if you do anything for it,

67
00:06:24,360 --> 00:06:26,360
no matter who you are,

68
00:06:26,360 --> 00:06:29,360
I'm pretty sure that I'll be able to take care of it for the rest of my life.

69
00:06:29,360 --> 00:06:31,360
It's just a matter of time.

70
00:06:31,360 --> 00:06:34,360
You know what, while we're at it, don't give a damn about it now.

71
00:06:34,360 --> 00:06:36,360
It's just a matter of time.

72
00:06:36,360 --> 00:06:38,360
It's just a matter of time.

73
00:06:38,360 --> 00:06:41,360
You know what, while we're at it, don't give a damn about it now.

74
00:06:41,360 --> 00:06:43,360
We're really not that far away yet.

75
00:06:43,360 --> 00:06:47,360
And we'll be taking care of it for the rest of our lives.

76
00:06:47,360 --> 00:06:49,360
It's just a matter of time.

77
00:06:49,360 --> 00:06:52,360
You know what, while we're at it,

78
00:06:52,360 --> 00:06:55,360
don't give a damn about it now.

79
00:06:55,360 --> 00:06:57,360
It's just a matter of time.

80
00:06:57,360 --> 00:07:00,360
You know what, while we're at it,

81
00:07:00,360 --> 00:07:03,360
no matter who you are,

82
00:07:03,360 --> 00:07:06,360
I'm pretty sure that I'll be able to take care of it for the rest of my life.

</details>

The output for all for all of the videos was pretty, but didn't quite output the 50K word requirement for NaNoGenMo, so I went to look for something longer, and found  [Neil Gaimain reading his *The Graveyard Book*](https://www.youtube.com/watch?v=S6EUIH02MKY), an 8 hour audio book read with a British accent. 

I ran it through the process, and the output was exactly what I'd hoped for. While there were bursts of repetition throughout, it had lots of very coherent sentences, even series of lines that seemed to be thematically grouped together. It was reasonably easy to see how a human could read these words and plausibly think they were what the midified voice was saying. 


 You can [watch the full video](https://www.youtube.com/watch?v=Zqx5lPcyGCc&t=25s) on youtube, but below are some examples of  of the example audio and transcripts.


<audio controls
  src="/words/assets/graveyard006.mp3"
  type="audio/mp3">
</audio>

<details>
<summary> Midified Transcript excerpt from Gaimidian Graveyard </summary>
1
00:00:00,000 --> 00:00:04,000
Where do you find the only mother that I cannot touch that I hear?

2
00:00:05,000 --> 00:00:07,000
Well, most people will stop.

3
00:00:07,000 --> 00:00:09,000
Kicking and catching and so.

4
00:00:10,000 --> 00:00:12,000
In the northwest, inside of the great garrison,

5
00:00:12,000 --> 00:00:14,000
there's a different kind of brain that's dangling.

6
00:00:14,000 --> 00:00:17,000
All of the undiability of the ground is a mess,

7
00:00:17,000 --> 00:00:19,000
but the friends of the great garrison hang on.

8
00:00:19,000 --> 00:00:21,000
Many animals are there,

9
00:00:21,000 --> 00:00:23,000
and most of them may be children of children

10
00:00:23,000 --> 00:00:26,000
who are dying before they sense what they're saying.

11
00:00:26,000 --> 00:00:30,000
How many things are there that I can go into my life when I want to?

12
00:00:31,000 --> 00:00:35,000
Well, I'm trying to pretend that I do not regret that nothing was done to change.

13
00:00:35,000 --> 00:00:37,000
But when the game was done,

14
00:00:37,000 --> 00:00:39,000
and we were at the old chapel,

15
00:00:39,000 --> 00:00:42,000
we broke two ribs that changed good-bye.

16
00:00:44,000 --> 00:00:46,000
The first one is old and bad.

17
00:00:47,000 --> 00:00:49,000
It was, or it was new,

18
00:00:49,000 --> 00:00:51,000
and when it came by its back,

19
00:00:51,000 --> 00:00:53,000
I was in bad.

20
00:00:53,000 --> 00:00:55,000
It was at least a hundred and fifty years old,

21
00:00:55,000 --> 00:00:57,000
I think I'm new.

22
00:00:57,000 --> 00:00:59,000
Back when I thought it was rough,

23
00:00:59,000 --> 00:01:01,000
if it was in a rough time,

24
00:01:01,000 --> 00:01:03,000
well, it turned out to be bad.

25
00:01:03,000 --> 00:01:05,000
It was going to look terrible.

26
00:01:05,000 --> 00:01:07,000
I had to take the knife and stab it.

27
00:01:07,000 --> 00:01:09,000
And we didn't know what to do with it.

28
00:01:09,000 --> 00:01:11,000
But I've never seen better than that before.

29
00:01:11,000 --> 00:01:13,000
I've never even noticed that.

30
00:01:13,000 --> 00:01:15,000
It's not that bad.

31
00:01:15,000 --> 00:01:17,000
But if it was better than that,

32
00:01:17,000 --> 00:01:19,000
it was always a problem.

33
00:01:19,000 --> 00:01:21,000
Well, I'm trying to keep inside it.

34
00:01:21,000 --> 00:01:23,000
But if it's old,

35
00:01:23,000 --> 00:01:25,000
and it's not,

36
00:01:25,000 --> 00:01:27,000
it was too heavy for me.

37
00:01:27,000 --> 00:01:29,000
That's the first thing.

38
00:01:29,000 --> 00:01:31,000
The second thing

39
00:01:31,000 --> 00:01:33,000
is sitting on the bench

40
00:01:33,000 --> 00:01:35,000
by the chapel.

41
00:01:35,000 --> 00:01:37,000
But, it's not it.

42
00:01:37,000 --> 00:01:39,000
It's way too bad.

43
00:01:41,000 --> 00:01:43,000
The second thing was not good.

44
00:01:45,000 --> 00:01:47,000
I think the church,

45
00:01:47,000 --> 00:01:49,000
and her restaurant,

46
00:01:49,000 --> 00:01:51,000
was a bit stupid.

47
00:01:51,000 --> 00:01:53,000
I know that is true,

48
00:01:53,000 --> 00:01:55,000
but the other thing was also a bit stupid.

49
00:02:25,000 --> 00:02:31,000
Thank you, and before you go to sleep, I have rented a room in your house over there.

50
00:02:31,000 --> 00:02:35,000
If I could go in, it'd be a lot more expensive.

51
00:02:35,000 --> 00:02:38,000
However, I still spend my time in this graveyard.

52
00:02:38,000 --> 00:02:42,000
I am here as a historian, presenting to you the story of Old Grey.

53
00:02:42,000 --> 00:02:45,000
Do you understand what I'm saying?

54
00:02:47,000 --> 00:02:48,000
What?

55
00:02:48,000 --> 00:02:49,000
This what?

56
00:02:49,000 --> 00:02:52,000
This boy, not boy.

57
00:02:52,000 --> 00:02:55,000
Just a nobody, you say.

58
00:02:55,000 --> 00:02:56,000
A foolish man.

59
00:02:56,000 --> 00:02:58,000
Also, boys is a dead man.

60
00:02:58,000 --> 00:02:59,000
A dead man.

61
00:02:59,000 --> 00:03:02,000
I do not believe.

62
00:03:02,000 --> 00:03:04,000
I will call you boys.

63
00:03:04,000 --> 00:03:07,000
You will call me misrepresenters.

64
00:03:07,000 --> 00:03:13,000
Boys, it would happen, perhaps, to you, but there is no proof of that at this place.

65
00:03:13,000 --> 00:03:21,000
If you do not think that I am dead, you can think that I am a misrepresenter, but I am sure the security will get on.

66
00:03:21,000 --> 00:03:22,000
What?

67
00:03:22,000 --> 00:03:25,000
This boy, not boy.

68
00:03:25,000 --> 00:03:28,000
She's not a boy.

69
00:03:28,000 --> 00:03:33,000
That, this fellow has been telling me since the beginning.

70
00:03:33,000 --> 00:03:36,000
I think we should apologize, don't you?

71
00:03:36,000 --> 00:03:40,000
Oh, this, this, this fellow has been coaching us.

72
00:03:40,000 --> 00:03:46,000
Tell me boys, the child in this boy's bag has actually been telling you how old he is, don't you say?

73
00:03:46,000 --> 00:03:49,000
I'm sorry, but what does that do?

74
00:03:49,000 --> 00:03:53,000
That girl, she did nothing in her life, you know, didn't she?

75
00:03:53,000 --> 00:03:54,000
Don't you think?

76
00:03:54,000 --> 00:03:57,000
I have come a long way from a godly boy.

77
00:03:57,000 --> 00:04:00,000
I hope you are worth it.

78
00:04:00,000 --> 00:04:04,000
God, could not imagine, honey, that would.

79
00:04:04,000 --> 00:04:06,000
Don't you know that you can?

80
00:04:06,000 --> 00:04:09,000
Who's that, if you don't understand this, honey?

81
00:04:09,000 --> 00:04:12,000
You don't think, boy, no, it's not a man.

82
00:04:12,000 --> 00:04:14,000
It is who you think I am.

83
00:04:14,000 --> 00:04:23,000
Then, just in the back of her bag, there's a boy who walks down the hall to the back of the room.

84
00:04:23,000 --> 00:04:26,000
Oh, it's cold as tarantula.

85
00:04:26,000 --> 00:04:28,000
What have you done?

86
00:04:28,000 --> 00:04:30,000
He says.

87
00:04:30,000 --> 00:04:31,000
Give me back.

88
00:04:31,000 --> 00:04:32,000
The window opens.

89
00:04:32,000 --> 00:04:33,000
It's me.

90
00:04:33,000 --> 00:04:35,000
Don't you worry, you're a black boy.

91
00:04:35,000 --> 00:04:39,000
I've got nothing to pay you, don't you say?

92
00:04:39,000 --> 00:04:44,000
If you don't say, that's when you were born, you promised that you would never leave me.

93
00:04:44,000 --> 00:04:45,000
You were kind to me.

94
00:04:45,000 --> 00:04:48,000
You knew that I was the man that you had.

95
00:04:48,000 --> 00:04:52,000
You're so reliable.

96
00:04:52,000 --> 00:04:54,000
I left the door open.

97
00:04:54,000 --> 00:04:56,000
Hmm, truly.

98
00:04:56,000 --> 00:04:57,000
You left the door open.

99
00:04:57,000 --> 00:05:00,000
You tried to leave, but it was as hard as always.

100
00:05:00,000 --> 00:05:03,000
And then you went to the door, and the door opened again.

101
00:05:03,000 --> 00:05:05,000
Did you get that right?

102
00:05:05,000 --> 00:05:06,000
Hmm.

103
00:05:06,000 --> 00:05:09,000
Well, I don't think I even tried.

104
00:05:09,000 --> 00:05:12,000
You know, when I was a kid, I didn't like kids.

105
00:05:12,000 --> 00:05:16,000
I just wanted to go outside, and the only thing I could do was cry.

106
00:05:16,000 --> 00:05:18,000
All the time.

107
00:05:18,000 --> 00:05:20,000
Up until the end of the day.

108
00:05:20,000 --> 00:05:22,000
I was a black boy.

109
00:05:22,000 --> 00:05:24,000
I was a tomboy.

110
00:05:24,000 --> 00:05:26,000
I did that every night, every morning.

111
00:05:26,000 --> 00:05:30,000
But the idea of going to the chapel, without knowing anything about it,

112
00:05:30,000 --> 00:05:34,000
was one of all our difficult situations before.

113
00:05:34,000 --> 00:05:38,000
And then, well, you know.

114
00:05:38,000 --> 00:05:40,000
You knew that I was the man that you had.

115
00:05:40,000 --> 00:05:41,000
You were kind to me.

116
00:05:41,000 --> 00:05:43,000
You knew that I was the man that you had.

117
00:05:43,000 --> 00:05:46,000
You did that every night, every morning.

118
00:05:46,000 --> 00:05:48,000
Up until the end of the day.

119
00:05:48,000 --> 00:05:50,000
I was a black boy.

120
00:05:50,000 --> 00:05:53,000
I was a tomboy.

121
00:05:53,000 --> 00:05:56,000
You knew that I was the man that you had.

122
00:05:56,000 --> 00:05:58,000
You did that every night, every morning.

123
00:05:58,000 --> 00:06:01,000
But the idea of going to the chapel, without knowing anything about it,

124
00:06:01,000 --> 00:06:03,000
was one of all our difficult situations before.

125
00:06:03,000 --> 00:06:05,000
And then, well, you know.

126
00:06:05,000 --> 00:06:07,000
You knew that I was the man that you had.

127
00:06:07,000 --> 00:06:09,000
You did that every night, every morning.

128
00:06:09,000 --> 00:06:11,000
Up until the end of the day.

129
00:06:11,000 --> 00:06:13,000
I was a Black Boy.

130
00:06:13,000 --> 00:06:15,000
I did that every morning.

131
00:06:15,000 --> 00:06:17,000
Up until the end of the day.

132
00:06:17,000 --> 00:06:19,000
I was a tomboy.

133
00:06:19,000 --> 00:06:21,000
I was a black boy.

134
00:06:21,000 --> 00:06:23,000
I did that every night, every morning.

135
00:06:23,000 --> 00:06:25,000
Up until the end of the day.

136
00:06:25,000 --> 00:06:27,000
I was a black boy.

137
00:06:27,000 --> 00:06:29,000
I was a tomboy.

138
00:06:29,000 --> 00:06:31,000
I did that every night, every morning.

139
00:06:31,000 --> 00:06:36,000
No one has ever heard of a movie character who can never live before.

140
00:06:36,000 --> 00:06:39,000
It's not horrible, you bet.

141
00:06:39,000 --> 00:06:43,000
If you do not think this movie is good, you bet.

142
00:06:43,000 --> 00:06:46,000
It will be more horrible.

143
00:06:46,000 --> 00:06:48,000
It will be told.

144
00:06:48,000 --> 00:06:50,000
No.

145
00:06:50,000 --> 00:06:52,000
More than 100.

146
00:06:52,000 --> 00:06:57,000
It is a magic tool that gives you the perfect way through and through.

147
00:06:57,000 --> 00:07:00,000
The movie is funny, but not so bad.

148
00:07:00,000 --> 00:07:02,000
It will get you down.

149
00:07:02,000 --> 00:07:06,000
Now, the characters have been presented.

150
00:07:06,000 --> 00:07:09,000
Some of them have been offered a chance to do the same thing.

151
00:07:09,000 --> 00:07:12,000
But who can do the same thing?

152
00:07:12,000 --> 00:07:14,000
Each group has a master.

153
00:07:14,000 --> 00:07:17,000
All of them have been rejected.

154
00:07:17,000 --> 00:07:21,000
All of them are going to be treated the same way as all of them.

155
00:07:21,000 --> 00:07:23,000
Each group is going to be together.

156
00:07:23,000 --> 00:07:25,000
And we are going to be part of it.

157
00:07:25,000 --> 00:07:27,000
We will do our best.

158
00:07:27,000 --> 00:07:31,000
These they are tiny groups.

159
00:07:31,000 --> 00:07:33,000
You can swing them.

160
00:07:33,000 --> 00:07:35,000
I'll be big.

161
00:07:35,000 --> 00:07:38,000
Mel, you throw a ball.

162
00:07:38,000 --> 00:07:40,000
You tumble like metal.

163
00:07:40,000 --> 00:07:43,000
Each ball was coming out from five.

164
00:07:43,000 --> 00:07:46,000
This is your chance to sit.

165
00:07:46,000 --> 00:07:48,000
No one can come close to you.

166
00:07:48,000 --> 00:07:50,000
No one can come.

167
00:07:50,000 --> 00:07:54,000
This time, we have to make a difference.

168
00:07:54,000 --> 00:07:56,000
And then it falls.

169
00:07:57,000 --> 00:08:00,000
So, this happens when the danger is not there.

170
00:08:00,000 --> 00:08:03,000
Two different kinds of churches down.

171
00:08:03,000 --> 00:08:05,000
This is happening at the top of the platform.

172
00:08:05,000 --> 00:08:08,000
They can get into a place similar to the church in bed.

173
00:08:08,000 --> 00:08:10,000
Two days and hours.

174
00:08:10,000 --> 00:08:12,000
That's all.

175
00:08:12,000 --> 00:08:14,000
It will come back.

176
00:08:14,000 --> 00:08:16,000
It will not get ruined down.

177
00:08:16,000 --> 00:08:18,000
It will go on and on.

178
00:08:20,000 --> 00:08:23,000
Then the next one will come back.

179
00:08:23,000 --> 00:08:25,000
This time it will go back to the church in bed.

180
00:08:25,000 --> 00:08:27,000
Then it will go on and on.

181
00:08:27,000 --> 00:08:29,000
It will try to get back to the floor.

182
00:08:29,000 --> 00:08:31,000
It's coming.

183
00:08:31,000 --> 00:08:33,000
Let's go.

184
00:08:33,000 --> 00:08:35,000
Then.

185
00:08:35,000 --> 00:08:37,000
You have the idea of the way to go.

186
00:08:37,000 --> 00:08:39,000
What do the teachers think?

187
00:08:39,000 --> 00:08:41,000
I have teachers.

188
00:08:41,000 --> 00:08:45,000
The teachers are the teachers we like to avoid.

189
00:08:45,000 --> 00:08:47,000
And the children of the teachers will be

190
00:08:47,000 --> 00:08:49,000
completely educational system

191
00:08:49,000 --> 00:08:51,000
for those who get hurt.

192
00:08:51,000 --> 00:08:53,000
The children of the teachers will be

193
00:08:53,000 --> 00:08:55,000
the ones most important.

194
00:08:57,000 --> 00:08:59,000
I do geography and everything.

195
00:08:59,000 --> 00:09:01,000
I don't need more lessons.

196
00:09:03,000 --> 00:09:05,000
You do everything then, Roy.

197
00:09:05,000 --> 00:09:07,000
It's your role.

198
00:09:07,000 --> 00:09:09,000
I know where it is.

199
00:09:09,000 --> 00:09:11,000
You know everything.

200
00:09:11,000 --> 00:09:13,000
How do you say that?

201
00:09:13,000 --> 00:09:15,000
This is just before the hour.

202
00:09:15,000 --> 00:09:17,000
Tell me about food.

203
00:09:17,000 --> 00:09:19,000
She said.

204
00:09:19,000 --> 00:09:21,000
All the times you remember what

205
00:09:21,000 --> 00:09:23,000
I have been told about food

206
00:09:23,000 --> 00:09:25,000
over the years.

207
00:09:25,000 --> 00:09:27,000
Keep away from them.

208
00:09:27,000 --> 00:09:29,000
She said.

209
00:09:29,000 --> 00:09:31,000
And that is all you know?

210
00:09:31,000 --> 00:09:33,000
No.

211
00:09:33,000 --> 00:09:35,000
Why do you keep away from them?

212
00:09:35,000 --> 00:09:37,000
Where do you come from?

213
00:09:37,000 --> 00:09:39,000
Where do you go?

214
00:09:39,000 --> 00:09:41,000
Why do you not stand near a food joint?

215
00:09:41,000 --> 00:09:43,000
Say it for me.

216
00:09:43,000 --> 00:09:45,000
What's wrong?

217
00:09:45,000 --> 00:09:47,000
She said.

218
00:09:47,000 --> 00:09:49,000
Why did I go back to that meaty house?

219
00:09:49,000 --> 00:09:51,000
When I first came home

220
00:09:51,000 --> 00:09:53,000
early in the morning

221
00:09:53,000 --> 00:09:55,000
and when I finished

222
00:09:55,000 --> 00:09:57,000
early in the morning

223
00:09:57,000 --> 00:09:59,000
in the half an hour

224
00:09:59,000 --> 00:10:01,000
I fell in

225
00:10:01,000 --> 00:10:03,000
In the half an hour

226
00:10:03,000 --> 00:10:05,000
No.

227
00:10:09,000 --> 00:10:11,000
I must've died.

228
00:10:11,000 --> 00:10:13,000
Are you better than this, Roy?

229
00:10:13,000 --> 00:10:15,000
I know we are better.

230
00:10:15,000 --> 00:10:20,000
You know, boy, there's nothing that you can't do now.

231
00:10:20,000 --> 00:10:24,000
And you're convinced that you will, will you work?

232
00:10:24,000 --> 00:10:25,000
This is our field.

233
00:10:25,000 --> 00:10:26,000
The living and the dead.

234
00:10:26,000 --> 00:10:28,000
There are day folks and night folks.

235
00:10:28,000 --> 00:10:31,000
There are ghouls and evil ghosts.

236
00:10:31,000 --> 00:10:34,000
There are high hunters and the hounds of God.

237
00:10:34,000 --> 00:10:37,000
Hold your breath, or you'll die.

238
00:10:39,000 --> 00:10:40,000
What do you do?

239
00:10:40,000 --> 00:10:42,000
I work.

240
00:10:42,000 --> 00:10:45,000
I do the telling.

241
00:10:45,000 --> 00:10:47,000
I'll win the best thing.

242
00:10:51,000 --> 00:10:53,000
I'm a pilot.

243
00:10:54,000 --> 00:10:56,000
She knows the best thing when she says,

244
00:10:57,000 --> 00:10:59,000
We're the best of the best.

245
00:11:00,000 --> 00:11:02,000
Boy, you do the best.

246
00:11:03,000 --> 00:11:06,000
The kind of people you think, the good people you can't take,

247
00:11:06,000 --> 00:11:07,000
They're the best of the best.

248
00:11:07,000 --> 00:11:08,000
Boy, you do the best.

249
00:11:08,000 --> 00:11:09,000
Boy, you do the best.

250
00:11:09,000 --> 00:11:11,000
The best of the best.

251
00:11:12,000 --> 00:11:14,000
And boys cannot be forced to work.

252
00:11:14,000 --> 00:11:15,000
If that ain't the case,

253
00:11:15,000 --> 00:11:19,000
Then we can ask for another pilot under the joke name.

254
00:11:20,000 --> 00:11:22,000
When the last thing we're dying of,

255
00:11:22,000 --> 00:11:23,000
I'll let you know,

256
00:11:23,000 --> 00:11:24,000
We'll pay.

257
00:11:24,000 --> 00:11:25,000
We'll let you play, mate,

258
00:11:25,000 --> 00:11:27,000
But now no one can go,

259
00:11:27,000 --> 00:11:29,000
Not until our last friend's gone.

260
00:11:30,000 --> 00:11:31,000
It's time to get done.

261
00:11:31,000 --> 00:11:33,000
Who is using existing software?

262
00:11:33,000 --> 00:11:35,000
This is a great job.

263
00:11:35,000 --> 00:11:40,000
If you're ready to go, get on.

264
00:11:40,000 --> 00:11:43,000
Enough of this地方,

265
00:11:43,000 --> 00:11:49,000
We think that the next step in the world is universal

266
00:11:49,000 --> 00:11:50,000
Come and get yourse riding away

267
00:11:50,000 --> 00:11:52,000
Time goes slowly,

268
00:11:52,000 --> 00:11:54,000
but I ain't a slowWhen Get yourse

269
00:11:54,000 --> 00:11:55,000
adelante

270
00:11:55,000 --> 00:11:58,000
I got things to do

271
00:11:58,000 --> 00:12:03,280
Every night when

272
00:12:03,280 --> 00:12:04,060
Damn,

273
00:12:04,060 --> 00:12:14,060
The two ladies were in a thing that they used to call the help in English language in the world.

274
00:12:14,060 --> 00:12:23,060
And she was elected in a hope that her family would get that good luck by the birthday she would find her in the land.

275
00:12:23,060 --> 00:12:34,060
Church, Old Detroit, Watto, S.O.S. We shall not belong to each other once again.

276
00:12:34,060 --> 00:12:36,060
Next world.

277
00:12:36,060 --> 00:12:40,060
Oh, isn't this stupid? I don't remember what it was called either.

278
00:12:40,060 --> 00:12:45,060
They had terrible things, and they blinded our world as well.

279
00:12:45,060 --> 00:12:51,060
This was a beautiful world, protected by the red stripes above those of our lives.

280
00:12:51,060 --> 00:12:55,060
I never gave too much of it.

281
00:12:55,060 --> 00:13:00,060
And now each room has the only dead room.

282
00:13:00,060 --> 00:13:02,060
Next world.

283
00:13:02,060 --> 00:13:07,060
Bored to make the money, you do it back to this door, which is this door.

284
00:13:07,060 --> 00:13:10,060
But just don't cry like a fool.

285
00:13:10,060 --> 00:13:12,060
Ah!

286
00:13:12,060 --> 00:13:14,060
Two dead.

287
00:13:14,060 --> 00:13:17,060
As it was before.

288
00:13:17,060 --> 00:13:21,060
Bored to death, until the day that silence was gone.

289
00:13:21,060 --> 00:13:28,060
He said, there's a different job in the train yard. Sometimes you're seen in the media. Would you go there?

290
00:13:28,060 --> 00:13:31,060
Mr. Death is dead, Mr. Death died.

291
00:13:31,060 --> 00:13:33,060
No, he said.

292
00:13:33,060 --> 00:13:35,060
Going down.

293
00:13:35,060 --> 00:13:36,060
What's the day?

294
00:13:36,060 --> 00:13:40,060
The morning of the day. I give you the night, and remember it for tomorrow.

295
00:13:40,060 --> 00:13:48,060
It's the death of the day, the day you can feel the hole in the white paper that makes no hole.

296
00:13:48,060 --> 00:13:53,060
Bored to death, until the day that silence was gone.

297
00:13:53,060 --> 00:13:57,060
He said, there's a different job in the train yard. Sometimes you're seen in the media.

298
00:13:57,060 --> 00:14:01,060
Bored to death, until the day that silence was gone.

299
00:14:01,060 --> 00:14:10,060
Now you're playing it in that way. You don't want to just play and you'll be told you're not going to find anything to do about it.

300
00:14:10,060 --> 00:14:15,060
He went down to the L.A. station to complain to his parents that he's been lying to that girl,

301
00:14:15,060 --> 00:14:19,060
where he's been against Mr. Death, and all that's hard for Mr. Death.

302
00:14:19,060 --> 00:14:22,060
He comes back down to his father, the children have.

303
00:14:22,060 --> 00:14:24,060
For the drug, the drug.

304
00:14:24,060 --> 00:14:28,060
And that's what he's telling all that he's saying, they've been sitting down with our friends,

305
00:14:28,060 --> 00:14:34,060
the children at the train yard, and how much he would have loved to learn about all the beautiful things that all we've learned,

306
00:14:34,060 --> 00:14:40,060
which was, as far as I've been going, we didn't learn.

307
00:14:40,060 --> 00:14:43,060
Aren't you going to meet that man anyway?

308
00:14:43,060 --> 00:14:49,060
They wouldn't know, unless we stick together in this mess.

309
00:14:49,060 --> 00:14:55,060
He's done talking to the train yard during the run, and under a bridge bridge.

310
00:14:55,060 --> 00:15:01,060
All the music out here just hit the road, and one of the children got kicked right down.

311
00:15:01,060 --> 00:15:06,060
He thought he was out there alone, and couldn't wait to see another kind of girl play with him.

312
00:15:06,060 --> 00:15:08,060
They kept him thinking.

313
00:15:08,060 --> 00:15:11,060
And one of my favorite girls tried to run for his life.

314
00:15:11,060 --> 00:15:15,060
Each day, one of these my friends found him dancing out of bed with one.

315
00:15:15,060 --> 00:15:25,060
Music.


</details>
<br>


## Next Steps

There are many places where you can really almost hear the human voice in the MIDI, but what I found most fascinating was the way that the text captions guided your brain into hearing words, even if those words weren't there in the original audio. The way thr brain fills in the gaps to try to make sense is absolutely fascinating to me and I'd like to explore this idea further. I think it can be used it as a way of making apparent how we can be guided into believing the "truth" of something based on the contextual framing.

I am thinking of an interface where the audio book plays, and there are two options for captions:
* Captions from the original audio
* Captions from the midified audio

Both options would be unlabeled, and it would be up to the viewer/listener to decide which one comes from the original audio and which one comes form the midified audio. It could almost be a game, with short clips of audio and the two sets of transcripts. The removal of the context of the previous sentence or nexxt sentence would make it even harder to recognize the midified captions as nonsensical because Whisper tends to create short burst of coherence.

A few issues need to be addressed though. 

Firstly, there is some difference between the length of the original audio and midified audio (midified audio being slightly longer), which throws off the timestamps for comparing captions from the two. Perhaps something as simple as speeding up the midified audio till its duration is the same length as the original?

Secondly, there is an issue with converting very long files to WAV, which is required to for the WAV to MIDI transformation. WAV files have a maximum size of 4GB, and being uncompressed audio, have a much larger size for the relative duration. 64 bit wave files can be produced to bypass this limit ([RF64](https://en.wikipedia.org/wiki/RF64)), but `waon` won't process them, so it doesn't help for this issue. Ultimately, it just adds some more steps of splitting and splicing into the mix, but it would be nice to avoid it.


## How I created these (on my mac)

Below are the commands I ran to process the files, probably mostly as a reminder to myself in the future. Thanks past me! You're welcome future me.

1. Download the mp3 directly or extract the youtube video audio as an mp3 with [yt-dlp](https://github.com/yt-dlp/yt-dlp)
   `yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=S6EUIH02MKY" --output myAudioBook.mp3`  
1. Convert mp3 to wav with [ffmpeg](https://ffmpeg.org/) 
    `ffmpeg -i myAudioBook.mp3 myAudioBook.wav`
1. Convert the wav file to midi with  [`waon`](http://kichiki.github.io/waon/)
   `waon -i myAudioBook.wav -o MyAudioBook.mid`
1. Convert the midi back to mp3 with [timidity](https://github.com/geofft/timidity) 
   `timidity myAudioBook.mid  -Ow -o - | ffmpeg -i - -acodec libmp3lame -ab 64k MyAudioBookMidified.mp3`
1. Try to extract text from the audio using [Whisper](https://github.com/openai/whisper) 
   `whisper --model large --language English MyAudioBookMidified.mp3` 
1. generate video from a gif that loops exactly as long as the audio track I'm about to include
`ffmpeg -stream_loop -1 -i MyAudioBook.gif -i MyAudioBookMidified.mp3 -vf crop=540:302:0:40,scale=1280:720,setsar=1,format=yuv420p -shortest -fflags +shortest -max_interleave_delta 100M -movflags +faststart MyAudioBookMidified.mp4`
1. Add the Whisper-generated srt to the video
`ffmpeg -i MyAudioBookMidified.mp4 -i MyAudioBookMidified.srt -c copy -c:s mov_text MyAudioBookMidifiedWithSrt.mp4`
