# Contribution Guide and Page Template

Use this page as the common maintenance guide for the site and as the skeleton for new pages.

## Repository Structure

```text
saashq-knowledge/
├── docs/
│   ├── CNAME
│   ├── index.md
│   ├── cloudflare-email-routing.md
│   ├── fleet-mdm.md
│   ├── page-template.md
│   └── assets/
│       └── <page-name>/
├── mkdocs.yml
├── requirements-docs.txt
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
```

## Contribution Rules

- Keep one page focused on one setup, decision, or repeatable procedure.
- Write in Markdown, not HTML.
- Store screenshots under `docs/assets/<page-name>/`.
- Use short lowercase filenames, for example `cloudflare-email-routing.md`.
- Add every public page to `nav` in `mkdocs.yml`.
- Keep real usernames, email addresses, tokens, phone numbers, and account IDs masked.
- Use placeholders such as `masked-destination@gmail.com` when the real value should not be public.
- Update `Last verified` only after real verification.
- Run `mkdocs build --strict` before publishing.

## LLM Update Rules

When an LLM updates this site:

- Preserve existing working commands and object names unless the user asks to change them.
- Do not invent verification results.
- Do not add category folders unless there are several pages that genuinely belong together.
- Prefer concise operational notes over long background explanation.
- Keep navigation small and obvious.
- If creating a new page, copy the skeleton below and add it to `mkdocs.yml`.

## Page Skeleton

Copy from here when adding a new page.

```markdown
# Page Title

Date: YYYY-MM-DD  
Status: Draft / Working / Verified / Deprecated  
System: Service, tool, device, or vendor name  
Owner: Person responsible for maintaining this page  
Sensitive data: Masked / Not applicable  
Last verified: YYYY-MM-DD

## Goal

Write the desired outcome in one or two sentences.

## When to Use This

Explain the situation where this page is useful.

## Final Configuration

- Domain/service:
- Account or tenant:
- Server or device:
- Important object names:
- Final working state:

## Prerequisites

- Account/access needed:
- DNS/server/app assumptions:
- Local tools needed:
- Risk or downtime:

## Steps

1. First step.
2. Second step.
3. Third step.

## Commands

Use this section only when commands are useful.

```bash
command goes here
```

## Screenshots

Add redacted screenshots here.

```markdown
![Screenshot title](assets/page-name/screenshot-redacted.png)
```

## Verification

- What was tested:
- Evidence:
- Expected result:
- Last verified result:

## Troubleshooting

| Symptom | Check | Fix |
| --- | --- | --- |
| Example problem | Where to look | What to change |

## LLM Maintenance Notes

When an LLM updates this page:

- Preserve real configuration values only if they are already public.
- Keep secret values masked.
- Prefer short steps over long explanation.
- Update `Last verified` only after actual verification.
- Add new screenshots under `docs/assets/<page-name>/`.
- Add or update `mkdocs.yml` navigation when creating a new page.

## Notes

Record limitations, surprises, or future cleanup here.
```
