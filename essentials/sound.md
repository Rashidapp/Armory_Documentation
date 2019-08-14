# Sound

Use `.wav` / `.flac` formats for sound files. During the build process, files are converted to best match the target platform. Use `Armory Project - Flags - Sound Quality` slider to tweak the quality.

## Playback State

When playing a sound, use the returned [audio channel](https://github.com/Kode/Kha/blob/master/Sources/kha/audio1/AudioChannel.hx) to query playback state.

```hx
var audioChannel: kha.audio1.AudioChannel =  iron.system.Audio.play(sound);
trace(audioChannel.position); // In seconds
trace(audioChannel.finished);
```
