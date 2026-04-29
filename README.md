# KCloud

`kcloud.sh` is a small Bash script for backing up and restoring KDE Plasma preferences.

It currently supports:

- Local backup of selected KDE and Plasma config files into a folder
- Local restore from a backup folder
- Uploading a backup to a GitHub gist as a tarball encoded as base64
- Downloading a gist backup and restoring it locally

The backup set is tuned for portability across different machines. It aims to preserve your Plasma layout, appearance, shortcuts, and app preferences while avoiding hardware-specific settings like monitor arrangements and input-device tuning.

## Usage

Run the script with no arguments for an interactive prompt:

```bash
./kcloud.sh
```

```bash
./kcloud.sh --backup [dest_dir]
./kcloud.sh --restore [src_dir]
./kcloud.sh --backup-gist [gist_id] [work_dir]
./kcloud.sh --restore-gist [gist_id] [dest_dir]
```

You can run it straight from `seglectic.com`:

```bash
curl -fsSL https://seglectic.com/scripts/kcloud.sh | bash
```

## Notes

- Gist sync uses the authenticated `gh` CLI session.
- If no gist ID is provided to `--backup-gist`, KCloud creates a new private gist.
- Backups may contain personal paths, hostnames, bookmarks, and other machine-specific settings.
- Hardware-specific settings such as display layout and per-device input tuning are intentionally excluded.
- Gist-backed backups can still include personal information such as SSH host aliases, bookmarks, local paths, widget/app state, and custom scripts. Keep gists private and review the backup set before syncing if you use work-only or sensitive resources.
- Restoring overwrites matching settings and creates `.kcloud-pre-restore.bak` copies where possible.

## Requirements

- `bash`
- `cp`, `tar`, `base64`
- `gh` for gist sync
- `jq` for gist download
