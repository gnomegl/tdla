# tdla - Telegram Download Assistant

[![Basher](https://img.shields.io/badge/basher-install-brightgreen)](https://github.com/basherpm/basher)

A convenient wrapper for `tdl` (Telegram Downloader) to export and download Telegram chats with ease.

## Features

- **Chat Export**: Export Telegram chat data to JSON format
- **Automatic Download**: Download media files from exported chats
- **Flexible Options**: Control message count, content inclusion, and output format
- **Skip Duplicates**: Avoid re-downloading existing files
- **Multiple Formats**: Support for various export options

## Installation

### Using Basher

```bash
basher install gnomegl/tdla
```

### Manual Installation

```bash
git clone https://github.com/gnomegl/tdla.git
cd tdla
chmod +x tdla
# Add to PATH or copy to /usr/local/bin
```

## Prerequisites

This tool requires `tdl` (Telegram Downloader) to be installed and configured:

```bash
# Install tdl
go install github.com/iyear/tdl@latest

# Configure tdl with your Telegram credentials
tdl login
```

## Usage

### Basic Usage

```bash
# Export and download a chat by ID
tdla <chat_id>

# Export last 100 messages with content
tdla <chat_id> --size 100 --with-content

# Export all messages
tdla <chat_id> --all

# Export in raw format
tdla <chat_id> --raw
```

### Options

- `--size, -s <number>` - Number of messages to export (default: all)
- `--with-content, -w` - Include message content in export
- `--all, -a` - Export all messages (overrides size limit)
- `--raw, -r` - Export in raw format

### Examples

```bash
# Export last 50 messages from a channel
tdla -1001234567890 --size 50

# Export all messages with full content
tdla -1001234567890 --all --with-content

# Export in raw format for processing
tdla -1001234567890 --raw
```

## How It Works

1. **Export**: Uses `tdl chat export` to create a JSON file with chat data
2. **Download**: Automatically runs `tdl dl` to download media files
3. **Organization**: Creates a directory named after the chat ID
4. **Deduplication**: Skips files that already exist locally

## Output Structure

```
<chat_id>/
├── <chat_id>.json          # Chat export data
├── photos/                 # Downloaded photos
├── videos/                 # Downloaded videos
├── documents/              # Downloaded documents
└── audio/                  # Downloaded audio files
```

## Requirements

- `tdl` - Telegram Downloader (must be installed and configured)
- `bash` - Shell environment

## License

MIT License
