# webm与mov视频格式

## webm
WebM is an open-source format developed by Google. It was mainly created for the purpose of sharing video files online and is supported by all major browsers, from Google Chrome to Microsoft Edge. As it contains small video files, it allows for almost immediate playback, making it great for websites with a lot of video content and one of the go-to options for live streaming platforms such as Streamlab.

## mov
MOV is a video file format that is most compatible with iOS devices, although it also works on Windows. It was developed by Apple with the main purpose of storing full-length movies. It supports high video bitrate, which also enables decent video quality. MOV is compatible with a long list of codecs and platforms. The best players to use to open MOV files are QuickTime and VLC.

## webm to mov

```sh
ffmpeg -i input.webm -c:v qtrle output.mov

```


## 参考

- [best-video-file-formats](https://target-video.com/best-video-file-formats)
