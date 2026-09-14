# Audio, Video, Sources, and Tracks

`video` and `audio` embed timed media. Native `controls` provide browser playback controls and are the safest default unless you build a complete accessible alternative. Multiple `source` elements let the browser choose a format it can play, and `poster` supplies an image before video playback.

```html
<video controls poster="preview.jpg">
  <source src="lesson.webm" type="video/webm">
  <source src="lesson.mp4" type="video/mp4">
  <track
    kind="captions"
    src="lesson-en.vtt"
    srclang="en"
    label="English"
    default>
</video>

<audio controls src="interview.mp3"></audio>
```

`track` attaches timed text such as captions or subtitles, commonly using WebVTT. Captions include speech plus relevant non-speech audio for people who cannot hear the soundtrack; subtitles mainly translate dialogue. A transcript is also valuable for searchability and non-audio contexts. Autoplay with sound is commonly blocked and is usually a poor user experience even when technically possible.
