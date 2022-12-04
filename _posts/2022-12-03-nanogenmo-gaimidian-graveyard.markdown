---
layout: post
title:  "Gaimidian Graveyard"
date:   2022-12-03 00:00:00 -0400
categories: ['audio', 'video', 'midi', 'nanogenmo', 'generative art']
---

This year, my plan for [NaNoGenMo](https://nanogenmo.github.io/) was to generate random noise that would be detected as words by speech-to-text processing, and use those to write a book. The idea was loosely inspired by [Reverse OCR bot](https://github.com/dariusk/reverseocr), which has always been one of my favorite projects that probes the absurd edges of what it means for a computer to "recognize" human language. 

Having absolutely no previous experience with audio Engineering, I wasn't really sure how to generate sounds that would be vaguely similar to the human voice. But when I came across Andy Baio's [*If Drake Was Born A Piano*](https://waxy.org/2015/12/if_drake_was_born_a_piano/) describing the disconcertingly nearly-human sound of a human voice in a song that has been converted to MIDI, I knew exactly what I wanted to do. 


So, the plan became:
1. Find a freely available mp3 audio book to download
2. Convert the mp3 to MIDI and the back to an mp3, thus creating an audio book with weirdly distorted speech
3. Run the midified-mp3 through OpenAI Whisper, the automated speech-recognition system
4. Hope the output is weird enough to make an interesting   #nanogenmo 

Unfortunately, my first attempts at the process didn't provide very good output from whisper.
It was often very low in content, or just a lot of repetition. I did notice, however, that some voices (or maybe recordings) seemed to fair a little better in terms of sounding like actual word, both to my ears and in terms of whisper detecting *something*  to transcribe.

I ran this with three sample mp3 first

<hr>
<br>
[Librivox recording of Jane Austen's *Emma*](https://ia803406.us.archive.org/20/items/emma_version_5_1002_librivox/emma_01_austen_64kb.mp3)

*Original Audio*

<audio controls>
  <source 
    src="https://ia803406.us.archive.org/20/items/emma_version_5_1002_librivox/emma_01_austen_64kb.mp3" type="audio/mp3">
</audio>

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
<br>
<hr>
<br>
[Will Self reading a Borges Story](https://static.guim.co.uk/audio/kip/books/series/books/1354894458366/9687/gdn.book.121215.tm.Will-Self-Jorge-Luis-Borges-story.mp3)

*Original Audio*

<audio controls>
  <source 
    src="https://static.guim.co.uk/audio/kip/books/series/books/1354894458366/9687/gdn.book.121215.tm.Will-Self-Jorge-Luis-Borges-story.mp3"
    type="audio/mp3">
</audio>

*Midified Audio*

<audio controls>
  <source 
    src="/words/assets/borges-roundtripped.mp3" type="audio/mp3">
</audio>

<details>
<summary>Transcribed midi</summary>
The procedure is here…
In the 12th and 15th of next year's time, I'll do a three-pointer.
In this empire, we are top of the three-pointer set.
That's the single spot of my empire.
That's the single spot of my empire.
Hitting the mine was done by a fellow named Haylike.
That's the spot for the three-pointer.
That's the land that I discovered in the past.
That's to be the victims' home in the end.
Of a creative constitution that I found at best if I opened it that day.
GTN 12���
One of the men.
Not without conflict, but they simply did it up,
they went to the bottom.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
I get down on my knees and think
that I can do more than I think.
It won't let me think
that I can do more than I think.
I can do it.
I'm not a fool.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
I get down on my knees and think
that I can do more than I think.
I can do it.
I'm not a fool.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
I get down on my knees and think
that I can do more than I think.
I can do it.
I'm not a fool.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
I get down on my knees and think
that I can do more than I think.
I can do it.
I'm not a fool.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
I get down on my knees and think
that I can do more than I think.
I can do it.
I'm not a fool.
The dead went to the grave,
but the exit moved for the first time,
and if I am,
but if I am, there is no other way.
I get down on my knees and think
that I can do more than I think.
I'm not a fool,
the dead went to the grave,
It's the end of the world, it's the end of the world.

</details>
<br>
<hr>
<br>

[An excerpt of James Earl Jones reading the bible](https://d3dqntzfhcgpyw.cloudfront.net/bk/topi/000001/bk_topi_000001_sample.mp3)

*Original Audio*

<audio controls>
  <source 
    src="https://d3dqntzfhcgpyw.cloudfront.net/bk/topi/000001/bk_topi_000001_sample.mp3"
    type="audio/mp3">
</audio>

*Midified Audio*

<audio controls>
  <source
  src="/words/assets/james-earl-jones-roundtripped.mp3"
  type="audio/mp3"
  >
</audio>

Then, on a whim, I tried 



## My full(ish) process
1. Download the youtube video as an mp3 with yt-dlp
   `yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=S6EUIH02MKY" --output myAudioBook.mp3`  
2. Convert mp3 to wav with ffmpeg 
    `ffmpeg -i myAudioBook.mp3 myAudioBook.wav`
2. Convert the wav file to midi with  [`waon`](http://kichiki.github.io/waon/)
   `waon -i myAudioBook.wav -o MyAudioBook.mid`
3. Convert the midi back to mp3 with timidity 
   `timidity myAudioBook.mid  -Ow -o - | ffmpeg -i - -acodec libmp3lame -ab 64k MyAudioBookMidified.mp3`
4. Try to extract text from the audio using Whisper 
   `whisper --model large --language English MyAudioBookMidified.mp3`

