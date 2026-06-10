# AGENTS.md

## Cursor Cloud specific instructions

PulseHub is a **static single-page app** (`index.html` only). There is no build step, package manager, or test suite.

### Running locally

Start a static HTTP server from the repo root (required — `file://` may break `fetch()`):

```bash
python3 -m http.server 8080
```

Open http://localhost:8080/

Use a tmux session if the server should stay running in the background.

### Services

| Service | Required | Port | Notes |
|---------|----------|------|-------|
| Static HTTP server | Yes | 8080 (or any free port) | `python3 -m http.server 8080` from `/workspace` |

No database, Docker, or backend services.

### External APIs

The app fetches data client-side from third-party APIs (OpenAlex, Algolia/HN, DEV.to, GitHub, Hugging Face, arXiv). Outbound HTTPS is required. **CORS and network policy vary by channel and environment** — in this Cloud VM, the **GitHub (OpenPulse)** channel reliably loads; other channels may fail with CORS or connection errors even when the static server is healthy.

### Lint / test

None configured. Verification is manual: serve `index.html` and confirm a channel loads content in the browser.

### Configuration

Inline constants in `index.html` (e.g. `ARXIV_CORS_PROXY`, `TR_EMAIL`). No `.env` loading.
