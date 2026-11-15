# Licar — Android APK

A prebuilt **Android port of [Licar](https://git.coom.tech/drummyfish/Licar)**, a small 3D racing game
by [drummyfish](https://git.coom.tech/drummyfish), released under **CC0** (public domain).

This repo just hosts the installable APK plus a short README — no source changes to the game itself
beyond a native Android frontend, which lives in the upstream fork on my machine.

## Download

Grab the APK from the [Releases](../../releases/latest) page, or download
[`licar.apk`](licar.apk) directly from this repo.

## Install

1. Copy `licar.apk` to the tablet (USB, cloud, or `adb install licar.apk`).
2. Tap it and allow "install unknown apps" for your file manager if asked.
3. It appears as a normal home-screen app called **Licar**. `adb install -r licar.apk` also works.

## Controls

Landscape only, fullscreen (system bars hidden). On-screen buttons:

| Button | Action |
| --- | --- |
| Right pad ▲ / ▼ | gas / brake–reverse |
| Right pad ◀ / ▶ | steer left / right |
| **B** | back / menu back |
| **A** | select / confirm |

## Technical notes

- `NativeActivity` with a native C frontend: software framebuffer blitted straight into
  `ANativeWindow`, AAudio for sound, no Gradle and no Java game code.
- Renders the game at 800×600 and integer-upscales 2× into the display, so it stays crisp and
  cheap on the GPU it doesn't use.
- Locked 30 fps; measured 30.3 fps on a Lenovo Tab M11 (Android 15, arm64-v8a).
- **Known wart:** starting a race takes ~25–30 s on that tablet while map geometry is built.
  That's CPU cost in the game itself, not the Android layer.

## License

The game and its assets are CC0 by drummyfish. The APK here is that code compiled for Android.
