# Saka for Cursor, Grok Bot, and future Grok marketplace

Saka business research and nine email marketing skills: free quotes, approved data purchases, lifecycle campaigns, and offline previews.

Bring a product brief, get a complete campaign and local preview, then research businesses when useful. The ten skills include Saka business research and all nine upstream email marketing skills. The plugin and skills are free; agent usage, email providers and optional purchased Saka data have separate costs. Saka is not an email sender. A purchased/public email address is not newsletter consent.

## Install

For Cursor CLI, load the checkout explicitly:

```sh
agent --plugin-dir /absolute/path/to/saka-cursor
```

For Cursor IDE, add this GitHub repository through the Plugins marketplace/custom repository flow supported by your account. For Grok Bot, use the shared Cursor/Grok plugin marketplace after publisher acceptance; local plugin directories are not a documented Grok Bot install route. Grok support is labeled **coming soon** by the submission form. This public source is not a marketplace listing. Do not claim installed or approved until the host confirms it.

## Connect and first use

1. Start with: **“Use email-marketing for my CSV reporting app. Draft an activation campaign and run the synthetic preview. Do not send or spend.”** No Saka account is needed for this work; Python 3.10+ is needed for the preview.
2. For real business research, sign in to Saka through your host's OAuth UI. `saka` connects to `https://saka.run/api/mcp`; `saka-library` connects to `https://saka.run/api/library/mcp`. Each audience needs its own authorization. Use library-only configuration if you only need existing purchases. See [authentication](https://saka.run/docs/auth).
3. Ask: **“Use saka-business to quote up to 5 US plumbing businesses, basic records, company grain. Show the price and evidence; do not purchase.”** Authentication is required, but quotes do not charge.
4. Purchase only with explicit authorization for the quoted cost and a maximum cap. The plugin exposes a spending tool; credentials alone are not permission. Preserve idempotency on retries. Never buy records just to test an install.

## Validate

```sh
python3 scripts/validate.py
python3 -m unittest discover -s tests -v
python3 skills/email-marketing/scripts/preview.py --help
python3 scripts/sandbox-check.py
```

The final check contacts Saka's no-account fictional sandbox and OAuth metadata. It sends no credentials, purchases nothing, and does not establish protected production tool acceptance. See [TESTING.md](TESTING.md) for host-specific acceptance and remaining limits.

## Provenance and maintenance

[Email Marketing Skills](https://github.com/email-marketing-skills/email-marketing-skills) is pinned in [UPSTREAM.json](UPSTREAM.json), including every vendored skill file hash. All required references and the preview script are bundled; no install-time downloads or hidden runtime are needed. Preserve attribution and re-run tests before updating those files. [Security](SECURITY.md) explains reporting and authority boundaries.
