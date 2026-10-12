# Malaysia Live TV (Unofficial Unifi Playlist Edition)

This repository keeps a Malaysia IPTV playlist at [live.txt](./live.txt) and an Android TV customization/build workflow under [android-app](./android-app).

## Streaming subscription

```text
https://raw.githubusercontent.com/wang0911-sys/unifi-tvbox/main/live.txt
```

## Android APK

- Source: [sakana164/mytv_android](https://github.com/sakana164/mytv_android) at commit `fc78a7f392f1552826c0bb2b06c8a817a4dd16ef`, GPL-3.0, based on Tian Guang Yun Ying.
- Customization patch: [patch_malaysia.py](./android-app/patch_malaysia.py), which changes the app name, package identity and initial IPTV source only.
- Build workflow: [build-malaysia-tv.yml](./.github/workflows/build-malaysia-tv.yml).
- On a successful build, an APK appears in [Releases](https://github.com/wang0911-sys/unifi-tvbox/releases), and in the successful [Actions run](https://github.com/wang0911-sys/unifi-tvbox/actions) as an artifact.

The Android player only indexes externally hosted streams; streams may expire or be geographically restricted. The app does not bypass operator IPTV authentication or network segmentation.

### Updating channels remotely

Edit [live.txt](./live.txt) and commit. In the player, use refresh/clear playlist cache to fetch updated content, or let the built-in 10-minute playlist cache expire. This does not require rebuilding/reinstalling the app.

### Important

This is an unofficial community build, not officially provided by Unifi or the original TV Live developers. Source is available from the linked original repository and the patch. If distributing an APK, comply with the original GPL-3.0 obligations. The CI build currently uses an ephemeral signing key: when rebuilding a newer APK it may be necessary to uninstall the previous build first, unless a persistent signing certificate is configured privately.
