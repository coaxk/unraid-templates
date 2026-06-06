# unraid-templates

Unraid Community Applications templates for
[subarr](https://github.com/coaxk/subarr).

- `templates/subarr.xml` — the CA container template for subarr.
- `images/subarr-icon.png` — the app icon.

## What is subarr?

The coordination layer for the *arr subtitle stack. It stands beside Bazarr,
never instead of it: Bazarr finds and downloads, subgen transcribes, and subarr
decides what subtitles are actually missing across Sonarr, Radarr and Bazarr,
verifies the spoken audio language by ear, and coordinates the work. Full
details in the [subarr repo](https://github.com/coaxk/subarr).

## Installing on Unraid

Search "subarr" in the **Apps** tab once it is live in Community Applications.

To add it manually: **Docker → Add Container → Template repositories**, add
`https://github.com/coaxk/unraid-templates`, then **Add Container** and choose
subarr from the template dropdown.

## Template notes

- subarr is CPU-only; no GPU is required (transcription is subgen's job).
- The SQLite database and persisted settings live in the Config (`/config`)
  appdata share.
- Integrations (Bazarr, Sonarr, Radarr, Tautulli, Plex, Ollama) are optional;
  the first-run onboarding wizard auto-detects them on your Docker network, and
  manual entry is available at every step.
- subarr needs a subgen container for transcription
  (`ghcr.io/coaxk/subarr-subgen` recommended; vanilla mccloudS/subgen works in
  compatibility mode).

## License

MIT. See [LICENSE](LICENSE).
