# ffmpegdestroy
Makes your video bad on purpose

```
ffmpeg.exe -i "video.mp4" -vf "scale=600:300" -filter:a "volume=1000" -b:v 100K -r 4 destroy1.mp4 && ffmpeg -i destroy1.mp4 -map 0:a -acodec libmp3lame output-audio.mp3 && ffmpeg -i output-audio.mp3 -i audio.mp3 -filter_complex "[0][1]amerge=inputs=2,pan=stereo|FL<c0+c1|FR<c2+c3[a]" -c:a libmp3lame -map "[a]" destroyfart.mp3 && ffmpeg.exe -i destroyfart.mp3 -b:a 50k -map a destroymp3.mp3 && ffmpeg -i "destroy1.mp4" -i destroymp3.mp3 -c copy -map 0:v:0 -map 1:a:0 destroy22.mp4
```
You ***need*** an input video with audio or not (itll merge existing audio), filename: video.mp4

And a audio file that is low quality or not (it might sound high quality with a non modified audio file), filename: audio.mp3

The output file is called destroy22.mp4, ima change the names later

### You __***NEED***__ [ffmpeg](https://ffmpeg.org).
