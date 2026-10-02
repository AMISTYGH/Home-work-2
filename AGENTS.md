# Eagle Eye Networks — Static Site

## Overview
Single-page static HTML website (`EagleEyeNetworks.html`). No backend, no database, no build step.

## Running
```bash
docker compose -f docker-compose.base44.yml up -d
```
Serves on port 3000 via nginx. The repo directory has restrictive permissions (700), so nginx runs its worker as `root` via a custom `nginx.conf`. The root `/` is configured to serve `EagleEyeNetworks.html` (via `default.conf`).

## Notes
- The HTML references `Style3.css` and `About me.html` which are not in the repo — the page loads without them but is unstyled.
- No credentials or external services required.
- Static files are served directly by nginx; edits are visible immediately on page refresh (call `reload_preview` to force the preview iframe to reload).
