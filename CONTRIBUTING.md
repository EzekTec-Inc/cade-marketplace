# Contributing to the Marketplace

Add your item under `catalog/` in a pull request. CI builds the catalog with your
item and checks it. Once your pull request is merged, the item is signed and published.

## What you can submit

| Kind | Where | Format | How to make it in the app |
|---|---|---|---|
| Plugin | `plugins/` | a `.tgz` plugin package (`manifest.json`, `package.json`, tool code) | Connectors → My Plugins → Build Plugin, or Pack Studio |
| WASM plugin | `plugins/<name>/` | a folder with `cade-plugin.json` and its Extism module | — |
| Workflow | `workflows/` | `<name>.cade-workflow.json` | Workflows → Export |
| Agent | `agents/` | `<name>.cade-agent.json` | Agents → Export |
| Skill | `skills/<name>/` | a folder with `SKILL.md` (frontmatter `name` and `description`), plus optional `scripts/`, `references/`, `assets/` | Lab → Skills |
| Widget | `widgets/` | `<name>.cade-widget.json` | Widgets → Export |

Give every item a clear name and description. A skill's `metadata.version` and
`metadata.author` in its frontmatter are shown in the app.

## Rules

- **You must have the right to publish it.** Submit only your own work, or work whose license
  allows redistribution. Say which license applies in the pull request.
- **No items taken from other products** whose licenses forbid redistribution, except the
  catalog's bundled plugin set added by the maintainers.
- **No secrets.** Leave out API keys, tokens and personal data. Plugins ask users for their own
  credentials.
- **Declare what a plugin does.** List its network domains and capabilities in its
  manifest's permissions. The build inspects the code, and fails when it finds a capability
  the manifest doesn't declare, such as network, filesystem, processes or environment.
- **One change per pull request.** To update an item, raise its version; old versions aren't
  kept in the catalog.

## Check it before you open the pull request

Download `cade-marketplace-linux-x86_64` from this repository's latest `tool-v*` release. Then:

```
chmod +x cade-marketplace-linux-x86_64
./cade-marketplace-linux-x86_64 build catalog /tmp/site
./cade-marketplace-linux-x86_64 verify /tmp/site
```

To try it in the app, add a source with the URL `file:///tmp/site/index.json` and no public
key. Then install your item from the Marketplace.

## Review

Maintainers check:

- that the item works;
- that its description is accurate;
- that its permissions are no broader than it needs;
- for plugins, that the code does what the description says.

Merging publishes the item.
