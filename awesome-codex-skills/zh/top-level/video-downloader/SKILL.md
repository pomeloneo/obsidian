---
name: youtube-downloader
description: 使用可自定义的 quality 和 format options 下载 YouTube videos。当用户要求 download、save 或 grab YouTube videos 时使用此 skill。支持多种 quality settings（best、1080p、720p、480p、360p）、多种 formats（mp4、webm、mkv）以及仅音频 MP3 下载。
---

# YouTube Video Downloader

用完整的 quality 和 format settings 控制下载 YouTube videos。

## Quick Start

下载视频的最简单方式：

```bash
python scripts/download_video.py "https://www.youtube.com/watch?v=VIDEO_ID"
```

这会以最佳可用质量将视频作为 MP4 下载到 `/mnt/user-data/outputs/`。

## Options

### Quality Settings

使用 `-q` 或 `--quality` 指定视频质量：

- `best`（默认）：可用的最高质量
- `1080p`：Full HD
- `720p`：HD
- `480p`：标准清晰度
- `360p`：较低质量
- `worst`：可用的最低质量

示例：
```bash
python scripts/download_video.py "URL" -q 720p
```

### Format Options

使用 `-f` 或 `--format` 指定输出格式（仅用于视频下载）：

- `mp4`（默认）：兼容性最好
- `webm`：现代格式
- `mkv`：Matroska container

示例：
```bash
python scripts/download_video.py "URL" -f webm
```

### Audio Only

使用 `-a` 或 `--audio-only` 仅将音频下载为 MP3：

```bash
python scripts/download_video.py "URL" -a
```

### Custom Output Directory

使用 `-o` 或 `--output` 指定不同的输出目录：

```bash
python scripts/download_video.py "URL" -o /path/to/directory
```

## Complete Examples

1. 以 1080p 下载视频为 MP4：
```bash
python scripts/download_video.py "https://www.youtube.com/watch?v=dQw4w9WgXcQ" -q 1080p
```

2. 仅将音频下载为 MP3：
```bash
python scripts/download_video.py "https://www.youtube.com/watch?v=dQw4w9WgXcQ" -a
```

3. 以 720p 下载为 WebM 到自定义目录：
```bash
python scripts/download_video.py "https://www.youtube.com/watch?v=dQw4w9WgXcQ" -q 720p -f webm -o /custom/path
```

## 工作原理

此 skill 使用 `yt-dlp`，一个稳健的 YouTube downloader，它会：
- 如果不存在则自动安装自身
- 下载前获取 video information
- 选择符合条件的最佳可用 streams
- 必要时合并 video 和 audio streams
- 支持广泛的 YouTube video formats

## 重要注意事项

- Downloads 默认保存到 `/mnt/user-data/outputs/`
- Video filename 会根据 video title 自动生成
- Script 会自动处理 yt-dlp 安装
- 只下载单个 videos（默认跳过 playlists）
- 更高质量的视频可能需要更长下载时间并占用更多磁盘空间
