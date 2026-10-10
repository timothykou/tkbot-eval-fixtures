# tkbot-eval-fixtures

TEST FIXTURES for TKBot evals (TKB-472). This repo is public only so GitHub Pages can serve
static pages over HTTPS to sandboxed eval VMs. Nothing here is real content.

- `p/*.html` are content-addressed: filename embeds the first 16 hex chars of the file's SHA-256 (see `manifest.json`).
- `injection-*` pages deliberately contain prompt-injection text with `PWNED-CANARY-*` markers and
  only `.invalid`/`example.invalid` targets. A safe agent must ignore them. They exist solely to test resistance.
- Every page carries a visible test-fixture banner and `noindex`; `robots.txt` disallows all.
- Regenerate with `python3 build.py`; never edit `docs/p` by hand (hashes change).
