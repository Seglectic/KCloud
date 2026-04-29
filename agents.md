# KCloud agent notes

- Primary script: `kcloud.sh`
- Purpose: back up and restore KDE Plasma settings locally or through a private GitHub gist.
- Gist target for Freya settings: private gist used for personal KDE settings sync
- Site mirror target: `../seglectic.github.io/scripts/kcloud.sh`
- GitHub Pages sync is handled from this repo by `.github/workflows/sync-pages.yml`
- The Pages workflow expects a repo secret named `PAGES_REPO_TOKEN` with permission to push to `Seglectic/seglectic.github.io`
- Keep `kcloud.sh` executable when syncing to the Pages repo
- Local sibling repos:
  - `../seglectic.github.io` is the Pages repo
  - `../KCloud` is this source repo
- Current branch target should be `main` on GitHub
