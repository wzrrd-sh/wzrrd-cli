---
name: wzrrd-publish
description: Publish static files or directories to wzrrd.sh. Use for sharing agent-built pages, demos, receipts, docs, diagrams, or static artifacts at https://<slug>.wzrrd.sh/.
---

# wzrrd publish

Use `wzrrd` to publish static files and directories to `https://<slug>.wzrrd.sh/`.

## Install

If `wzrrd` is missing:

```bash
curl -fsSL https://wzrrd.sh/install.sh | bash
```

If `~/.local/bin` is not on PATH, add it or call `~/.local/bin/wzrrd` directly.

## Publish immediately

```bash
wzrrd publish --file ./site --slug demo
```

- `--file` can be a single HTML file or a directory with `index.html` at the root.
- Anonymous publishes work without login.
- Anonymous publishes are ephemeral and expire after 24 hours.
- Anonymous responses include `claimUrl`; share/open it if the user wants the URL to become permanent.

## Permanent publishing

```bash
wzrrd login
wzrrd publish --file ./site --slug demo
```

`wzrrd login` runs a device approval flow and stores a scoped agent token at `~/.config/wzrrd/auth.json`.

## Safety defaults

- Published sites are `noindex` by default.
- Only add `--index` when the user explicitly wants search indexing.
- Prefer small static artifacts. Current anonymous limits are aggressive: 5 MB total, 1 MB per file, 50 files, 10 anonymous publishes per IP/hour.

## Diagnostics

Before debugging, run:

```bash
wzrrd doctor && wzrrd auth-status
```

## Return format

Always give the user the live URL. If the publish was anonymous, also include the `claimUrl` and remind them it expires in 24 hours unless claimed.
