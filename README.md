# YTubeMateX

A Python-based Android app built with Kivy for downloading YouTube videos, converting to MP3, and playing videos with background audio support.

## Features

- **YouTube Video Download**: Download videos in highest available quality
- **MP4 to MP3 Conversion**: Convert downloaded videos to MP3 format
- **Embedded Video Player**: Play YouTube videos directly in the app
- **Background Audio Playback**: Play MP3 files in the background
- **MP3 Download**: Direct MP3 download from YouTube videos
- **Modern UI**: Clean, intuitive interface with color-coded buttons

## Setup

### Prerequisites

1. **Python 3.7+** installed on your system
2. **Kivy** development environment set up
3. **Android SDK** and **NDK** (for Android builds)

### Installation

1. **Clone or download** this project
2. **Install Python dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the app locally**:
   ```bash
   python main.py
   ```

### Building for Android

1. **Install Buildozer**:
   ```bash
   pip install buildozer
   ```

2. **Initialize Buildozer** (if not already done):
   ```bash
   buildozer init
   ```

3. **Build the Android APK**:
   ```bash
   buildozer -v android debug
   ```

4. **Install on device**:
   ```bash
   buildozer android deploy run
   ```

## Usage

1. **Enter YouTube URL**: Paste any YouTube video URL in the input field
2. **Download Video**: Click "Download Video" to save the video file
3. **Convert to MP3**: Click "Convert to MP3" to create an audio file
4. **Play Video**: Click "Play Video" to open embedded YouTube player
5. **Download MP3**: Click "Download MP3" for direct audio download
6. **Background Playback**: Use "Play Background" to play MP3 files in background
7. **Stop Audio**: Click "Stop Audio" to stop background playback

## File Structure

```
YTubeMateX/
├── main.py              # Main application logic
├── ytubematx.kv         # Kivy UI layout
├── requirements.txt     # Python dependencies
├── buildozer.spec      # Android build configuration
├── README.md           # This file
└── downloads/          # Downloaded files (created automatically)
```

## Android Permissions

The app requires the following Android permissions:
- `INTERNET`: For downloading videos and accessing YouTube
- `WRITE_EXTERNAL_STORAGE`: For saving downloaded files
- `READ_EXTERNAL_STORAGE`: For accessing downloaded files
- `WAKE_LOCK`: For background audio playback
- `FOREGROUND_SERVICE`: For background services

## Troubleshooting

### Common Issues

1. **"No module named 'pytube'"**:
   ```bash
   pip install pytube --upgrade
   ```

2. **WebView not working on Android**:
   - Ensure `kivy-webview` is properly installed
   - Check Android WebView is enabled on device

3. **Audio playback issues**:
   - Verify audio files are properly downloaded
   - Check device audio settings

4. **Buildozer build failures**:
   - Update Buildozer: `pip install buildozer --upgrade`
   - Clean build: `buildozer android clean`
   - Check Android SDK/NDK versions

### Development Notes

- Files are downloaded to the `downloads/` directory
- MP3 conversion is done by renaming audio streams (no actual conversion)
- Background playback uses Kivy's SoundLoader
- Video player uses embedded YouTube iframe

## Legal Notice

This app is for educational purposes. Please respect YouTube's Terms of Service and copyright laws. Only download content you have permission to download.

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source and available under the MIT License. 