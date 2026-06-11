# wzrrd CLI

Public distribution repo for the `wzrrd` CLI and agent skill.

Install:

```bash
curl -fsSL https://wzrrd.sh/install.sh | bash
```

The installer downloads the latest release binary for your platform from this repo.

Latest release source version: `v0.4.1`

## Release assets

- `wzrrd-darwin-arm64`
- `wzrrd-darwin-x64`
- `wzrrd-linux-x64`
- `checksums.txt`

## Agent skill

The `wzrrd-publish` skill lives in `skills/wzrrd-publish`.

## Install the agent skill

```bash
npx skills add wzrrd-sh/wzrrd-cli --skill wzrrd-publish -g
```
