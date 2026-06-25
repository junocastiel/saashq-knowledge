# SaasHQ Knowledge Site

This folder contains a MkDocs Material static knowledge website.

The site is intentionally small right now:

- Cloudflare Email Routing
- Cloudflare Tunnel Local Preview
- Fleet MDM
- iPhone Appium Control
- Contribution Guide and Page Template

## Edit Content

Write pages in Markdown under `docs/`.

Put screenshots under `docs/assets/<topic-name>/`.

For a new page:

1. Copy `docs/page-template.md`.
2. Save it under `docs/` with a short lowercase filename.
3. Add it to `nav` in `mkdocs.yml`.
4. Run the strict build.

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
