ffmpeg-webm-scripts
===================

Currently two scripts, reverse and backforth script.
Reverse just reverses the whole thing and backforth goes forth first and then back again.
Loop with 4chan x or this [webm looper userscript](https://github.com/WhatIsThisImNotGoodWithComputers/webm-looper-userscript).

Normally you would use ffmpeg to create a 4khan webm like this:

```bash
ffmpeg -i chinese-cartoon.mkv -ss 00:01:54.239 -to 00:01:56.992 -c:v libvpx -crf 4 -b:v 4500K -vf scale=-1:-1 -an output.webm
```

For my scripts the following parameters are available `i:s:t:o:f:c:a:`, of these `i:s:t:` are required.
In the same order they are input file, start time, stop time, output file (default: output.webm), framerate (default 4500K), crop and scale. Order of crop and scale is important! Decide if you want to crop or scale first, input parameters in that order.

Examples:

Example 1: No fancy stuff like cropping or scaling. `test1.webm` is generated with the following command:

```bash
ffmpeg-webm-backforth -i \[Watakushi\]\ Akuma\ no\ Riddle\ -\ 04\ \[720p\]\[5A124B29\].mkv -s 00:01:00.000 -t 00:01:02.000 -o test1.webm
```

Example 2: Cropping first, then scaling. `test2.webm` is generated with the following command:

```bash
ffmpeg-webm-backforth -i \[Watakushi\]\ Akuma\ no\ Riddle\ -\ 04\ \[720p\]\[5A124B29\].mkv -s 00:01:00.000 -t 00:01:02.000 -o test2.webm -c 474:720:726:0 -a -1:400
```
