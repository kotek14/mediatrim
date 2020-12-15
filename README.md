# mediatrim
Quick and dirty media trimmer based on ffmpeg.

Trims the input file (first argument) from start time (second argument) to end time (third argument) and saves the result to the output file (fourth argument).

You can use `start` or `end` for start time and end time respectively to trim from the beginning or to the end of the file.

Make sure not to use `start` and `end` at the same time because you'll just get an ffmpeg error.

```
./mediatrim video.mp4 01:35 02:00 trimmed.mp4
./mediatrim video.mp4 start 02:00 trimmed.mp4
./mediatrim video.mp4 01:35 end trimmed.mp4
```

# mediatrim-slow
Same as mediatrim, but instead of using ffmpeg `copy` magic it just rerenders the trimmed video. For some reason `copy` drops some frames in the beginning, so if you're in the situation like that you better use the slower resourse-hungry `mediatrim-slow`.
