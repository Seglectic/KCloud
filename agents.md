# KCloud agent notes

- Primary script: `kcloud.sh`
- Purpose: reusable KDE Plasma settings backup and restore tool for both public use and personal reuse later.
- Keep tracked docs and commits generic. Do not store private gist IDs, secret repo details, or machine-specific personal notes in the repo.
- Gist sync is name-based now. Prefer human-readable backup names and local env vars like `KCLOUD_GIST_NAME` or `KBACK_GIST_NAME` instead of tracking gist IDs.
- KCloud backup gists are detected heuristically by the presence of `kcloud-backup.tar.gz.b64` and `kcloud-manifest.json`.
- Large gist restores must fetch the backup file via the gist file `raw_url`, not the inline API `content`, because GitHub truncates large file content in gist metadata.
- Streamed execution such as `curl ... | bash` must keep prompts reading from `/dev/tty` when available, or interactive mode will loop on empty stdin.
- Site mirror target: `../seglectic.github.io/scripts/kcloud.sh`
- GitHub Pages sync is handled from this repo by `.github/workflows/sync-pages.yml`
- The Pages workflow expects a repo secret named `PAGES_REPO_TOKEN` with permission to push to `Seglectic/seglectic.github.io`
- Keep `kcloud.sh` executable when syncing to the Pages repo
- Local sibling repo: `../seglectic.github.io` is the Pages repo.
- Local source repo: `../KCloud` is this repo.
- Current branch target should be `main` on GitHub
