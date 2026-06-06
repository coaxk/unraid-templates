# unraid-templates

Unraid Community Applications (CA) templates for **subarr** (and, later,
`subarr-subgen`).

- `templates/subarr.xml` — the CA container template for
  [subarr](https://github.com/coaxk/subarr).
- `images/subarr-icon.png` — the app icon CA displays (512x512).

## Status: staged, not yet announced

The template is ready. Before submitting to Community Applications, two things
still need doing (the actual "deploy" step):

1. **Create an Unraid forum support thread** for subarr (Docker Containers
   board) and set `<Support>` in `subarr.xml` to its URL. Right now `<Support>`
   points at the GitHub issues page as an interim; CA expects a forum thread.
2. **Announce this repo** in the Unraid forums "All Unraid Application Template
   Repositories / Support Threads" thread so the CA app feed picks it up.

## Decisions baked in

- **DB lives in `/config`** (`SUBARR_DB_PATH=/config/subarr.db`), the Unraid
  appdata convention. The subarr image default is `/data`; it is env-driven, so
  the template overrides it to `/config`.
- **No GPU** in the template. subarr is CPU-only; the GPU work is subgen's. A
  future `subarr-subgen.xml` will carry the nvidia runtime config.
- **PUID 99 / PGID 100** (Unraid `nobody:users`).
- All integrations (Bazarr/Sonarr/Radarr/Tautulli/Plex/Ollama) are optional and
  masked; the first-run onboarding wizard auto-detects them.

## Testing the template locally

On an Unraid box: **Docker → Add Container → Template repositories**, add this
repo's URL, then **Add Container → Template dropdown → subarr**.
