# gecko-docs

The public documentation site for **Gecko** — the API comprehension layer for agents.
Built with [Mintlify](https://mintlify.com).

This repo is **docs only**. The product engine lives in the `surfcall` repo (the
engine keeps its codename); these pages describe it and must stay accurate to it.

## Structure

```
gecko-docs/
├── docs.json            # Mintlify config: theme, colors, navigation
├── llms.txt             # agent-discoverability map for this site
├── introduction.mdx     # Get Started
├── quickstart.mdx
├── concepts.mdx
├── comprehension.mdx    # How it works
├── recorded-mode.mdx
├── access-and-auth.mdx
├── mcp.mdx              # For AI agents
├── discoverability.mdx
├── architecture.mdx     # Reference
├── status.mdx
├── favicon.png          # (asset — add)
└── logo/
    ├── light.svg        # (asset — add)
    └── dark.svg         # (asset — add)
```

## Run locally

Install the Mintlify CLI and serve from the repo root (the directory containing
`docs.json`):

```bash
npm i -g mint
mint dev
```

The site is served at `http://localhost:3000`. Use `mint dev --port 3333` to change
the port, and `mint broken-links` to validate internal links before publishing.

## Deploy

Mintlify deploys from the connected Git repo: install the Mintlify GitHub App on this
repository, and every push to the production branch — `main` — triggers an automatic
build and deploy. There is no separate build step — `docs.json` plus the MDX pages are
the source of truth.

## Assets still needed

These are referenced by `docs.json` but not yet committed — add them before deploy:

- `favicon.png`
- `logo/light.svg` and `logo/dark.svg`

## Adding the API tab later

When a hosted OpenAPI surface is ready, add an interactive playground by appending a
tab to `navigation.tabs` in `docs.json`:

```json
{
  "tab": "API Reference",
  "openapi": "https://<host>/openapi.json"
}
```

## Editing principles

- **Honest status first.** Match the `surfcall` engine repo README's tone — state what
  is live (the comprehension path on one real API) and what is not (multi-API, data
  verification).
- **Lead with the $0 recorded path.** A reader must be able to see it work with no key
  and no subscription.
- **Every command must run as written.** If something needs a key or a subscribe, say
  so up front.
- **Public-safe.** No pricing, business strategy, internal roadmap framing, partner
  names, or competitive comparisons.
