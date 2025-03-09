# YouTube Downloader Automated Script

![GitHub repo size](https://img.shields.io/github/repo-size/complexorganizations/youtube-download-script)
![GitHub stars](https://img.shields.io/github/stars/complexorganizations/youtube-download-script?style=social)
![GitHub forks](https://img.shields.io/github/forks/complexorganizations/youtube-download-script?style=social)

A robust shell script designed to automate the download of YouTube videos and extract audio using a simple command-line interface. Built on the reliable [`yt-dlp`](https://github.com/yt-dlp/yt-dlp) tool, this script is ideal for everyday users and content enthusiasts—no Git installation required—while also offering advanced options for developers who wish to contribute.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
  - [For End Users](#for-end-users)
  - [For Developers](#for-developers)
  - [Install Dependencies](#install-dependencies)
- [Usage](#usage)
  - [Basic Usage](#basic-usage)
  - [Downloading a Single Video](#downloading-a-single-video)
  - [Extracting Audio Only](#extracting-audio-only)
- [Advanced Usage](#advanced-usage)
  - [Specifying Output Format](#specifying-output-format)
  - [Downloading in Specific Formats](#downloading-in-specific-formats)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [Video Player Recommendation](#video-player-recommendation)
- [License](#license)

## Features

- **Seamless Downloads:** Easily download YouTube videos and playlists.
- **Audio Extraction:** Extract and convert audio (e.g., MP3) for music or podcasts.
- **Optimized Quality:** Automatically selects the best available video and audio quality.
- **Flexible Formats:** Supports multiple formats such as MP4, MKV, and WebM.
- **User-Friendly CLI:** Minimal setup for everyday users, with advanced options for developers.

## Installation

### For End Users

For most users, installing the script is as simple as downloading it via `curl`. No Git installation is required:

```bash
curl -o yt-dlp-auto.sh https://raw.githubusercontent.com/complexorganizations/youtube-download-script/main/yt-dlp-auto.sh
chmod +x yt-dlp-auto.sh
```

### For Developers

Developers who wish to contribute or build upon the script can clone the repository using Git:

```bash
git clone https://github.com/complexorganizations/youtube-download-script.git
cd youtube-download-script
chmod +x yt-dlp-auto.sh
```

### Install Dependencies

The script requires [`yt-dlp`](https://github.com/yt-dlp/yt-dlp) and `ffmpeg`. Install them with your preferred package manager:

**For Linux (Debian/Ubuntu):**

```bash
sudo apt update
sudo apt install yt-dlp ffmpeg -y
```

**For macOS (using Homebrew):**

```bash
brew install yt-dlp ffmpeg
```

**For Windows (using Chocolatey):**

```bash
choco install yt-dlp ffmpeg
```

For additional installation details, see the [yt-dlp installation guide](https://github.com/yt-dlp/yt-dlp#installation).

## Usage

### Basic Usage

Run the script directly to initiate the download process:

```bash
bash yt-dlp-auto.sh
```

The script will guide you through its options based on your configuration.

### Downloading a Single Video

To download a video in the best available quality, use:

```bash
yt-dlp -f "bestvideo+bestaudio/best" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

For a specific resolution (e.g., 1080p), use:

```bash
yt-dlp -f "bestvideo[height=1080]+bestaudio/best[height=1080]" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

### Extracting Audio Only

Extract and convert the audio (e.g., to MP3) with:

```bash
yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

## Advanced Usage

### Specifying Output Format

Customize the output filename and destination with the `--output` option:

```bash
yt-dlp --output "~/Downloads/%(title)s.%(ext)s" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

This command saves the video in your Downloads folder using its title as the filename.

### Downloading in Specific Formats

To download a video in a particular format (such as MP4), specify the format code:

```bash
yt-dlp -f "mp4" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

## Troubleshooting

- **Missing `yt-dlp` Command:** Verify that `yt-dlp` is installed by following the dependency instructions above.
- **Permission Issues:** Ensure the script is executable using `chmod +x yt-dlp-auto.sh`.
- **Quality Settings:** The script automatically selects the best quality by default. Use the `-f` flag for custom quality settings.
- **SSL/TLS Errors:** Run `sudo apt-get update` on Linux or `brew update` on macOS to update your package lists, or reinstall `yt-dlp` if you encounter SSL/TLS issues.

## Contributing

We welcome contributions! If you’re a developer interested in enhancing this script, follow these steps:

1. **Fork the repository.**
2. **Create a feature branch:**
   ```bash
   git checkout -b feature-branch
   ```
3. **Commit your changes:**
   ```bash
   git commit -am 'Add new feature'
   ```
4. **Push to your fork:**
   ```bash
   git push origin feature-branch
   ```
5. **Submit a pull request** targeting the `main` branch.

Please ensure that your code is well-documented and aligns with the existing coding style.

## Video Player Recommendation

For optimal playback, we recommend [VLC Media Player](https://www.videolan.org/), known for its extensive format support and reliability.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/complexorganizations/youtube-download-script/blob/main/license.md) file for more details.
