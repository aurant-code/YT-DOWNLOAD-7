# Video Saver 2.0

A Kotlin + Jetpack Compose Android app that saves videos you're allowed to download straight into your Gallery.

## Features
- **Gallery album:** videos are saved to `Movies/Video Saver`, which shows up as a "Video Saver" album in Google Photos / Gallery.
- **Share to save:** in a browser or any app, tap **Share → Video Saver** and the download starts automatically. Direct video links can also be opened with **Open with → Video Saver**.
- **Link check:** before downloading, the app confirms the link is a single video file (MP4, WebM, MOV, MKV, 3GP…). Web pages and streaming playlists get a clear message instead of a broken download.
- **Download history:** progress bars while downloading; then Play, Share or Delete for each video. Failed downloads can be retried. History is kept between launches.
- **Background downloads:** uses Android's DownloadManager, so downloads continue if you leave the app, with a system notification.
- **No storage permission needed** (Android 10+). Follows your phone's light/dark theme and Material You colors.

## What it won't download
- **YouTube:** links open in the YouTube app. Use YouTube's own Download button (YouTube Premium), or YouTube Studio → Download for your own uploads.
- **Web pages / streaming sites:** the link must point directly to a video file. Only save videos you own or have permission to download.

## Build in Android Studio
1. Unzip and choose **Open**, then select the `VideoSaverProject` folder.
2. Let Gradle sync finish (use JDK 17 if asked).
3. Plug in your phone with USB debugging on (Android 10+) and press **Run**, or use **Build → Build APK(s)**. The APK is at `app/build/outputs/apk/debug/app-debug.apk`.

## Build without Android Studio (GitHub Actions)
1. Push this folder to a GitHub repository.
2. **Actions** tab → **Build APK** runs automatically (or click **Run workflow**).
3. Download `VideoSaver-debug-apk` from the run's **Artifacts** and install `app-debug.apk` on your phone.

## Project layout
- `MainActivity.kt` — screen, share handling, history list, play/share/delete actions.
- `VideoRepository.kt` — link checking, DownloadManager downloads, Gallery scanning, saved history.
