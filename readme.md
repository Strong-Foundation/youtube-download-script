# YouTube Downloader Automated Script

![GitHub repo size](https://img.shields.io/github/repo-size/complexorganizations/youtube-download-script) ![GitHub stars](https://img.shields.io/github/stars/complexorganizations/youtube-download-script?style=social) ![GitHub forks](https://img.shields.io/github/forks/complexorganizations/youtube-download-script?style=social)

This shell script automates the process of downloading YouTube videos and optionally extracting audio, all through a simple command-line interface. It leverages `yt-dlp`, a popular tool that supports downloading videos and playlists from YouTube and other websites.

## Features

- **Download YouTube videos** directly from URLs.
- **Extract audio** from YouTube videos, perfect for music or podcasts.
- Automatically selects the **best available video and audio quality**.
- Supports downloading videos in different formats, including MP4, MKV, and WebM.
- Provides a simple command-line interface with minimal setup required.

## Installation

To get started with the YouTube downloader script, follow these installation steps.

### 1. Clone the repository or download the script directly using `curl`:

```bash
curl https://raw.githubusercontent.com/complexorganizations/youtube-download-script/main/yt-dlp-auto.sh -o yt-dlp-auto.sh
```

Alternatively, download the script manually from [this link](https://raw.githubusercontent.com/complexorganizations/youtube-download-script/main/yt-dlp-auto.sh).

### 2. Make the script executable:

```bash
chmod +x yt-dlp-auto.sh
```

### 3. Install Dependencies (if necessary):

The script relies on the `yt-dlp` tool, which may not be pre-installed on your system. You can install it using the following commands:

**For Linux (Debian/Ubuntu):**

```bash
sudo apt update
sudo apt install yt-dlp
```

**For macOS (using Homebrew):**

```bash
brew install yt-dlp
```

**For Windows (via Chocolatey):**

```bash
choco install yt-dlp
```

Alternatively, you can manually install `yt-dlp` by following the [official installation instructions](https://github.com/yt-dlp/yt-dlp#installation).

## Usage

Once the script is installed and dependencies are in place, you can use it to download YouTube videos or audio.

### 1. Running the Script

To run the script and download a video, use the following command:

```bash
sudo bash yt-dlp-auto.sh
```

This will start the download process based on the configuration within the script.

### 2. Download a Single Video

To download a specific YouTube video, simply use the following command (replace the URL with the desired video URL):

```bash
yt-dlp -f "bestvideo+bestaudio/best" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

This will download the best quality video and audio available for the provided URL.

### 3. Extract Audio Only

If you only need the audio (e.g., for podcasts or music), you can use the `-x` option to extract audio in your desired format (e.g., MP3, AAC):

```bash
yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

This will download and convert the audio to MP3 format.

## Advanced Usage

### 1. Specify Output Format

You can specify the output file name and format using the `-o` option. For example, to save the video as `my_video.mp4`, use the following command:

```bash
yt-dlp -o "~/Downloads/%(title)s.%(ext)s" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

This will save the video with its title as the filename.

### 2. Download in Specific Formats

If you want to download a video in a specific format (e.g., MP4, WebM), you can use the `-f` flag with the format code. For example:

```bash
yt-dlp -f "mp4" "https://www.youtube.com/watch?v=WZeZZ8_W-M4"
```

## Troubleshooting

- **Missing `yt-dlp` Command**: Ensure `yt-dlp` is properly installed. Follow the installation instructions above.
- **Permission Issues**: If you encounter permission issues while running the script, make sure you’ve granted the script execute permissions using `chmod +x yt-dlp-auto.sh`.
- **Video/Audio Quality Issues**: `yt-dlp` automatically selects the best quality, but you can specify custom formats if needed. Use the `-f` option for more control over video and audio quality.
- **SSL/TLS Errors**: If you’re getting SSL/TLS errors, update your `yt-dlp` installation or try running `sudo apt-get update` (for Linux) or `brew update` (for macOS).

## Contributing

We welcome contributions to improve the functionality and features of this script. Here's how you can contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push to your fork (`git push origin feature-branch`).
5. Create a pull request to the `main` branch.

Please ensure that your code is well-documented and follows the existing code style.

## Video Player

To play downloaded videos, you can use any media player, but we recommend [VLC Media Player](https://www.videolan.org/) for its wide range of supported formats.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/complexorganizations/youtube-download-script/blob/main/license.md) file for more details.
