# SaasHQ Knowledge Site

This folder contains a MkDocs Material static knowledge website.

## Edit Content

Write pages in Markdown under `docs/`.

Common places:

- `docs/execution-logs/` for completed technical work with evidence.
- `docs/runbooks/` for repeatable procedures.
- `docs/infrastructure/` for Cloudflare, VPS, DNS, hosting, and backup notes.
- `docs/device-management/` for Android Enterprise, Fleet MDM, Headwind MDM, and device notes.
- `docs/decisions/` for comparisons and final decisions.
- `docs/troubleshooting/` for symptoms and fixes.
- `docs/page-templates/` for reusable page templates.

Put screenshots under `docs/assets/<topic-name>/`.

## Local Preview

```bash
python3 -m venv .venv-docs
.venv-docs/bin/python -m pip install -r requirements-docs.txt
.venv-docs/bin/mkdocs serve -a 127.0.0.1:8001
```

Open:

```text
http://127.0.0.1:8001/
```

## Build

```bash
.venv-docs/bin/mkdocs build --strict
```

The static output is generated in `site/`.

## Publish

For Cloudflare Pages or GitHub Pages, use:

- Build command: `pip install -r requirements-docs.txt && mkdocs build`
- Output directory: `site`

Before publishing, scan for sensitive text:

```bash
rg -ni "real-username|real-email@example.com" docs mkdocs.yml
```
