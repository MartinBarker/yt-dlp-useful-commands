# yt-dlp-useful-commands

Useful commands/scripts that I use with **yt-dlp** to download and manage YouTube videos, playlists, and audio files efficiently.

## 1. Download YouTube Playlist (No Overwrites, HQ mp3 + Artwork)

This command downloads every video in a YouTube playlist, converts them to the highest audio quality (mp3), tags the artwork using the video thumbnail, and splits any videos with chapters (like full album videos) into individual files. The audio files are saved in the format "title - uploader", and it will not overwrite files already downloaded.

### Usage:

Save this as `Download-Playlist.sh` and run it using:

```bash
./Download-Playlist.sh
```

### Command:

```bash
yt-dlp --download-archive downloaded.txt --split-chapters --no-post-overwrites -ciwx -f bestaudio --extract-audio --audio-format mp3 --audio-quality 0 --output "%(title)s - %(uploader)s.%(ext)s" --embed-thumbnail https://www.youtube.com/playlist?list=PLpQuORMLvnZalrprMzVbej685R_w7D6os
```

## 2. Download a Single Song (HQ mp3 + Artwork)

Use this command to download a single YouTube video as high-quality audio (mp3). It extracts the best available audio, converts it to mp3, and embeds the video thumbnail as the cover art.

### Command:

```bash
yt-dlp -x --audio-format mp3 --audio-quality 0 --embed-thumbnail --output "%(title)s.%(ext)s" https://www.youtube.com/watch?v=VIDEO_ID
```

Replace `VIDEO_ID` with the actual video URL or ID you want to download.

## 3. Download Video, Keep Specific Chapters Only

This command downloads a video, splits it based on chapters, and keeps only the chapters you specify while deleting the rest. For example, if you want to keep only chapter 2, this command will download and keep only that chapter.

### Command:

```bash
yt-dlp --split-chapters --match-title "Chapter 2" --output "%(chapter_title)s.%(ext)s" https://www.youtube.com/watch?v=VIDEO_ID
```

Replace `VIDEO_ID` with the actual video URL or ID. You can modify `"Chapter 2"` to match the specific chapter you want to keep.

---

These commands are optimized for handling YouTube playlists and single videos with yt-dlp. Feel free to modify the commands based on your specific needs!
