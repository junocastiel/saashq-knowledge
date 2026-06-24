# SaasHQ Knowledge Base

This site keeps practical technical setup notes in Markdown.

The goal is not to learn HTML. The goal is to record what was configured, why it was configured, how to repeat it, and how to verify that it still works.

## Current Pages

- [Cloudflare Email Routing](cloudflare-email-routing.md): how to catch email for `mdm.saashq.in` and forward it without hosting a mail server.
- [Cloudflare Tunnel Local Preview](cloudflare-tunnel-local-preview.md): how to expose a local website through a temporary Cloudflare Tunnel.
- [Fleet MDM](fleet-mdm.md): how Fleet MDM is running on macOS with Docker or OrbStack, Cloudflare Tunnel, and Android Enterprise.

## How to Add a Page

1. Copy [Contribution Guide and Page Template](page-template.md).
2. Save it as a short lowercase file name under `docs/`, for example `docs/new-service-setup.md`.
3. Put screenshots under `docs/assets/<page-name>/`.
4. Add the page to `nav` in `mkdocs.yml`.
5. Run `mkdocs build --strict`.

## Writing Rules

- Keep one page focused on one setup or decision.
- Prefer exact final configuration over long background explanation.
- Include verification commands or screenshots.
- Mask usernames, personal email addresses, tokens, account IDs, and phone numbers.
- Use placeholders like `masked-destination@gmail.com` when the real value should not be public.
