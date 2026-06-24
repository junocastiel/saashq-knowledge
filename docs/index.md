# Technical Knowledge Base

This site is for preserving technical execution notes, repeatable runbooks, infrastructure decisions, and troubleshooting references.

The goal is simple: write Markdown, add screenshots, publish a static site.

## How to Add a New Page

1. Copy the template from [Execution Note Template](page-templates/execution-note-template.md).
2. Save the new file under the best category.
3. Put screenshots under `docs/assets/<topic-name>/`.
4. Link screenshots using normal Markdown image syntax.
5. Build or publish the site.

## Categories

| Category | Use for |
| --- | --- |
| Execution Logs | What was actually done, with evidence and screenshots. |
| Runbooks | Repeatable procedures that can be followed later. |
| Infrastructure | Cloudflare, VPS, DNS, tunnels, email, backup, and hosting notes. |
| Device Management | Android Enterprise, Fleet MDM, Headwind MDM, Xiaomi device handling. |
| Decisions | Comparisons, tradeoffs, and final choices. |
| Troubleshooting | Symptoms, causes, fixes, and verification steps. |
| Templates | Reusable page formats. |

## Current References

- [Cloudflare Email Routing for Fleet MDM](execution-logs/cloudflare-mdm-email-routing.md)
