# video不同浏览器的表现

## autoplay policy

### ios webkit 

[*New video Policies for iOS*](https://webkit.org/blog/
6784/new-video-policies-for-ios/)

video autoplay elements will now honor the autoplay attribute, for elements which meet the following conditions:
- video elements will be allowed to autoplay without a user gesture if their source media contains no audio tracks.

- video muted elements will also be allowed to autoplay without a user gesture.

- If a video element gains an audio track or becomes un-muted without a user gesture, playback will pause.

- video autoplay elements will only begin playing when visible on-screen such as when they are scrolled into the viewport, made visible through CSS, and inserted into the DOM.

- video autoplay elements will pause if they become non-visible, such as by being scrolled out of the viewport.

video elements will now honor the play() method, for elements which meet the following conditions:

- video elements will be allowed to play() without a user gesture if their source media contains no audio tracks, or if their muted property is set to true.

- If a video element gains an audio track or becomes un-muted without a user gesture, playback will pause.

- video elements will be allowed to play() when not visible on-screen or when out of the viewport.

- video.play() will return a Promise, which will be rejected if any of these conditions are not met.

On iPhone, video playsinline elements will now be allowed to play inline, and will not automatically enter fullscreen mode when playback begins.

video elements without playsinline attributes will continue to require fullscreen mode for playback on iPhone.

When exiting fullscreen with a pinch gesture, video elements without playsinline will continue to play inline.

## Chrome

[Chrome 中的自动播放政策](https://developer.chrome.com/blog/autoplay?hl=zh-cn)

Chrome 的自动播放政策很简单：

- 始终允许静音自动播放。
- 在下列情况下，允许有声自动播放：
   - 用户与网域进行了互动（点击、点按等）。
   - 在桌面设备上，用户的媒体互动指数阈值已经超过，这意味着用户之前播放过有声视频。
   - 用户已在移动设备上将该网站添加到其主屏幕，或在桌面设备上安装了 PWA。
- 顶级帧可以将自动播放权限委托给其 iframe，以允许有声自动播放。

## X5浏览器

[x5内核 video问题](https://x5.tencent.com/docs/questions.html)

- 支持自动静音播放

## 微信浏览器
[Android微信内网页音频自动播放能力调整](https://developers.weixin.qq.com/community/develop/doc/000e640d77cfa001132a6cb8456c01?highLine=%25E5%25BE%25AE%25E4%25BF%25A1%25E7%25BD%2591%25E9%25A1%25B5%2520%25E8%25A7%2586%25E9%25A2%2591%2520autoplay)

- 安卓微信不支持autoplay属性
- IOS微信支持autoplay属性
 
相关的解决办法：https://developers.weixin.qq.com/community/develop/doc/000644bcbc0460ea28199e55d52000?highLine=%25E5%25BE%25AE%25E4%25BF%25A1%25E7%25BD%2591%25E9%25A1%25B5%2520%25E8%25A7%2586%25E9%25A2%2591%2520autoplay

## video常见问题

### video播放时报parse error的问题

这种情况通常是视频编码问题，以及视频封面poster的链接错误导致的

### [微信IOS获取摄像头video不播放的问题](https://developers.weixin.qq.com/community/develop/doc/00084ef48ec418bb060114fb66b800?highLine=getUserMedia%2520ios)

解决办法： https://developers.weixin.qq.com/community/develop/doc/00084ef48ec418bb060114fb66b800?highLine=getUserMedia%2520ios
