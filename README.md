# tdla

[![basher install](https://www.basher.it/assets/logo/basher_install.svg)](https://www.basher.it/package/)

telegram download assistant - tdl wrapper

## install

```bash
basher install gnomegl/tdla
```

## usage

```bash
tdla <chat_id> [options]
```

Exports and downloads Telegram chat media through `tdl`.

By default, `tdla` resumes from the last message it previously downloaded for the chat. It stores checkpoints in `./.tdla-state/` after successful downloads. If no checkpoint exists, it tries to derive the last downloaded message ID from existing files in the download directory using `tdl`'s default filename template.

## options

- `-n, --namespace, --ns <namespace>` - tdl namespace
- `-s, --size <number>` - export the last N messages instead of resuming
- `-w, --with-content` - include message content in export
- `-a, --all` - include non-media messages in export
- `-r, --raw` - include raw Telegram message structs
- `--from-beginning, --no-resume` - ignore checkpoints and export all matching messages
- `--state-dir <dir>` - checkpoint directory (default: `./.tdla-state`)

## requirements

- tdl
- curl
- jq