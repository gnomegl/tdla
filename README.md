# tdla

[![basher install](https://www.basher.it/assets/logo/basher_install.svg)](https://www.basher.it/package/)

telegram download assistant - tdl wrapper

## install

```bash
basher install gnomegl/tdla
```

## usage

```bash
tdla [command] [options]
```

export and download telegram chats.

## commands

- `export` - export chat messages
- `download` - download media files
- `list` - list available chats
- `search` - search messages

## options

- `-c, --chat` - chat id or username
- `-l, --limit` - message limit
- `-f, --format` - export format (json/csv/html)
- `-o, --output` - output directory

## requirements

- tdl
- curl
- jq