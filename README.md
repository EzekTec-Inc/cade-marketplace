# CADE Community Marketplace

Plugins, workflows, agents, skills and widgets for [CADE AGNTS](https://github.com/EzekTec-Inc/cade-agnts),
contributed here and published as a signed catalog:

**https://ezektec-inc.github.io/cade-marketplace/index.json**

CADE AGNTS has this catalog built in as **CADE Community** (Marketplace → Sources). The app
lists it only when its signature verifies against this public key:

```
FpmzBIgAYLBXulgWvZ2j80da++kTXy7siL6t+xk6xxw=
```

Files are downloaded only when you install them, and are checked against the SHA-256 in the
signed index first. Plugin packages are also inspected on your computer, and you're asked
before they install.

## Contents

```
catalog/        what contributors add (pull requests)
  plugins/      *.tgz plugin packages, or WASM plugin folders
  workflows/    *.cade-workflow.json
  agents/       *.cade-agent.json
  skills/       <name>/SKILL.md folders (with any scripts/, references/, assets/)
  widgets/      *.cade-widget.json
        │
        ▼  .github/workflows/publish.yml runs `cade-marketplace build`
GitHub Pages    index.json, index.json.sig, files/<kind>/<name>-<version>.<ext>
```

- **The `cade-marketplace` tool** reads items with the same code CADE AGNTS uses, so a catalog
  that builds is one the app can install. CI uses the Linux build attached to this
  repository's `tool-v*` release, checked against a SHA-256 pinned in the workflow.
- **Folder items** (skills, WASM plugins) are packed reproducibly: the same source always gives
  the same file and checksum.
- **Pull requests** are built unsigned as a check. Only `main` is signed and published.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Each item is under the license its contributor states
in its pull request.

## Maintainers

- **Signing.**
  - The repository secret `MARKETPLACE_SIGNING_KEY` holds the private key (PKCS#8, base64).
  - The variable `MARKETPLACE_PUBLIC_KEY` holds the public key above, which CI verifies
    against.
  - Rotating the key needs a CADE AGNTS release with the new public key. Plan rotations, and
    announce them.
- **Pages.** Settings → Pages → Source: **GitHub Actions**.
- **Updating the tool:**
  1. Attach a new `cade-marketplace-linux-x86_64` binary to a `tool-v<version>` release.
  2. Update `TOOL_TAG` and `TOOL_SHA256` in `.github/workflows/publish.yml`.
