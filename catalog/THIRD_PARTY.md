# Third-party material in the catalogue

Items below were taken from other projects under licences that allow redistribution and
modification. Each item keeps its source's licence text (`LICENSE` or `LICENSE.txt`) and, for
skills, a `NOTICE` listing what was changed. Sources were fetched on 2026-11-16 at the commits
given. Items not listed here are this catalogue's own or were added before this file existed.

## Skills (`skills/<name>/`)

| Item | Source | Commit | Licence | Changed |
|---|---|---|---|---|
| frontend-design | https://github.com/anthropics/skills/tree/main/skills/frontend-design | e4bb5d960d87126ff3b3a8af1a104b7db67560ba | Apache-2.0 (Anthropic, PBC) | Frontmatter rewritten (one-sentence description, licence, metadata, `allowed-tools` in this app's tool names); one sentence names `analyze_image`; attribution footer. Modified file. |
| theme-factory | https://github.com/anthropics/skills/tree/main/skills/theme-factory | e4bb5d960d87126ff3b3a8af1a104b7db67560ba | Apache-2.0 (Anthropic, PBC) | Frontmatter rewritten; step 1 lists the themes and points to `theme-showcase.pdf` instead of displaying it; duplicated word removed; footer. `themes/` and the PDF unchanged. Modified file. |
| ux-copy | https://github.com/anthropics/knowledge-work-plugins/tree/main/design/skills/ux-copy | e91a134584eb798bac7fb0379358006a2b63b965 | Apache-2.0 (repository LICENSE; Anthropic) | Frontmatter rewritten, `argument-hint` dropped; slash-command usage and `CONNECTORS.md` pointer removed; `~~connector` placeholders rewritten as plain guidance; footer. Modified file. |
| design-critique | https://github.com/anthropics/knowledge-work-plugins/tree/main/design/skills/design-critique | e91a134584eb798bac7fb0379358006a2b63b965 | Apache-2.0 (repository LICENSE; Anthropic) | As ux-copy, and `$ARGUMENTS`/`@$1` replaced by a "Getting the Design" section (`analyze_image`, `read_file`, optional Figma tool). Modified file. |
| build-dashboard | https://github.com/anthropics/knowledge-work-plugins/tree/main/data/skills/build-dashboard | e91a134584eb798bac7fb0379358006a2b63b965 | Apache-2.0 (repository LICENSE; Anthropic) | Frontmatter rewritten; slash-command usage, `CONNECTORS.md` pointer and `/build-dashboard` prefixes removed; "data warehouse is connected" generalised; footer. Modified file. |
| web-accessibility | https://github.com/addyosmani/web-quality-skills/tree/main/skills/accessibility | afa8da942115f2961fdbfa80807ea0b232ff6c00 | MIT (Addy Osmani) | Renamed from `accessibility`; frontmatter rewritten; testing note names `execute_shell_command` and a Chrome DevTools MCP server; link to the unbundled web-quality-audit skill removed; footer. |
| core-web-vitals | https://github.com/addyosmani/web-quality-skills/tree/main/skills/core-web-vitals | afa8da942115f2961fdbfa80807ea0b232ff6c00 | MIT (Addy Osmani) | Frontmatter rewritten; `references/MEASUREMENT.md` and `references/RUM.md` copied unchanged from `skills/performance/references/` and links pointed at them; link to the unbundled performance skill removed; footer. |
| visual-design-foundations | https://github.com/wshobson/agents/tree/main/plugins/ui-design/skills/visual-design-foundations | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | Frontmatter rewritten; "Reference Files" section listing `references/`; footer. |
| design-system-patterns | https://github.com/wshobson/agents/tree/main/plugins/ui-design/skills/design-system-patterns | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As visual-design-foundations. |
| interaction-design | https://github.com/wshobson/agents/tree/main/plugins/ui-design/skills/interaction-design | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As visual-design-foundations. |
| responsive-design | https://github.com/wshobson/agents/tree/main/plugins/ui-design/skills/responsive-design | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As visual-design-foundations. |
| frontend-slides | https://github.com/zarazhangrui/frontend-slides | 9906a34d640d2111f724544cbc50f7f130569ae1 | MIT (Zara Zhang) | Frontmatter rewritten; `bold-template-pack/` left out (drawn from a separate template library whose licence was not verified) and its instructions replaced by presets or a custom design; `scripts/deploy.sh` and `scripts/export-pdf.sh` (bash, Vercel CLI, Playwright) left out and Phase 6 rewritten as browser print-to-PDF and static hosting; file opening uses `open`/`start`/`xdg-open`; `scripts/extract-pptx.py`, `STYLE_PRESETS.md`, `html-template.md`, `animation-patterns.md`, `viewport-base.css` unchanged; footer. |
| web-interface-guidelines | https://github.com/vercel-labs/web-interface-guidelines/blob/main/command.md | 434b7f91364665f2f733b310ec54809bf8f37937 | MIT (Vercel Labs) | Made into a skill: `command.md` with new frontmatter and its `$ARGUMENTS` line replaced by instructions naming this app's file tools; rules and output format unchanged; footer. |
| systematic-debugging | https://github.com/obra/superpowers/tree/main/skills/systematic-debugging | 22f0b463e7a5e579904dd6211a520321035526f7 | MIT (Jesse Vincent) | Frontmatter rewritten; references to two unbundled superpowers skills replaced by the practice each stands for; `find-polluter.sh` (bash) left out and `root-cause-tracing.md` describes the bisection by hand; footer. |

`allowed-tools` in these skills uses this app's tool names (`read_file`, `write_file`,
`edit_file`, `list_files`, `grep_files`, `glob_files`, `execute_shell_command`,
`analyze_image`). None of the sources declared `allowed-tools`, so no names were mapped from
another client's; the app shows the field and does not enforce it.

## Agents (`agents/*.cade-agent.json`)

All agents use the catalogue's existing field conventions (provider `gemini`, model
`gemini-4-argon`, status `ACTIVE`, credit limit 1000). Every agent's system prompt is the
source definition's body, unchanged except as noted, followed by a "Working in CADE AGNTS"
section (tools, skills to load with `activate_skill`, the batch's plugins, and a rule against
reporting results that were not obtained) and an attribution line. Descriptions were rewritten
as one sentence; the source frontmatter (`model`, `color`, `tools`) was dropped and tools were
assigned from this app's tool ids.

| Item | Source | Commit | Licence | Changed |
|---|---|---|---|---|
| UI Designer | https://github.com/wshobson/agents/blob/main/plugins/ui-design/agents/ui-designer.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| Design System Architect | https://github.com/wshobson/agents/blob/main/plugins/ui-design/agents/design-system-architect.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| Accessibility Expert | https://github.com/wshobson/agents/blob/main/plugins/ui-design/agents/accessibility-expert.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| Frontend Developer | https://github.com/wshobson/agents/blob/main/plugins/frontend-mobile-development/agents/frontend-developer.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| UI Visual Validator | https://github.com/wshobson/agents/blob/main/plugins/accessibility-compliance/agents/ui-visual-validator.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| Code Reviewer | https://github.com/wshobson/agents/blob/main/plugins/comprehensive-review/agents/code-reviewer.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| Debugger | https://github.com/wshobson/agents/blob/main/plugins/debugging-toolkit/agents/debugger.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| Performance Engineer | https://github.com/wshobson/agents/blob/main/plugins/application-performance/agents/performance-engineer.md | 9c61ab243def98f72da12abd41cfcf5bcd91af9d | MIT (Seth Hobson) | As above. |
| UX Microcopy Reviewer | https://github.com/VoltAgent/awesome-claude-code-subagents/blob/main/categories/08-business-product/ux-microcopy-reviewer.md | ed74d115b7fb7026a22a4f816a8e3250f425e3b4 | MIT (VoltAgent; the file says it comes from the MIT plugin Clagoss/claude-code-para-disenadores) | As above; "subagent" in its disclosure line reads "reviewer". |
| UX Researcher | https://github.com/VoltAgent/awesome-claude-code-subagents/blob/main/categories/08-business-product/ux-researcher.md | ed74d115b7fb7026a22a4f816a8e3250f425e3b4 | MIT (VoltAgent) | As above; the context-manager JSON protocol, the progress-tracking JSON, the sample "delivery notification" with made-up figures and the list of other agents removed; a paragraph added on what it can and cannot do and on never inventing participants or metrics. |

The MIT licence texts for these agents: wshobson/agents, Copyright (c) 2024 Seth Hobson;
VoltAgent/awesome-claude-code-subagents, Copyright (c) 2025 VoltAgent. Both are the standard
MIT licence ("Permission is hereby granted, free of charge, … The above copyright notice and
this permission notice shall be included in all copies or substantial portions of the
Software. THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND …"); the full texts
are at the sources' `LICENSE` files and in `licenses/` below.

## Plugins (`plugins/*.agnt`)

| Item | Source | Version | Licence | Changed |
|---|---|---|---|---|
| svg-optimizer: `node_modules/svgo/dist/svgo.browser.js` | https://www.npmjs.com/package/svgo (tarball https://registry.npmjs.org/svgo/-/svgo-3.3.2.tgz) | svgo 3.3.2, sha512-OoohrmuUlBs8B8o6MB2Aevn+pRIH9zDALSR+6hhqVfa6fRwG/Qw9VUMSMW9VNg2CFc/MTIfabtdOVl9ODIJjpw== | MIT (Kir Belevich); bundled dependencies MIT, ISC, BSD-2-Clause, BSD-3-Clause, CC0-1.0 | Unchanged file. `package.json` trimmed to name, version, licence and the `./browser` export; `LICENSE`, `README.md` and `THIRD_PARTY_LICENSES.txt` (the bundled dependencies' licence texts) included. svgo 4.x was not used because its parser dependency `sax` 1.6.1 is BlueOak-1.0.0. |

The other five plugins (color-contrast-checker, color-palette-generator,
type-scale-calculator, design-token-converter, iconify-icon-search) and svg-optimizer's own
code are original to this catalogue, GPL-3.0-or-later (full text in each package's
`LICENSE`). They implement published formulas and formats: WCAG 2.2 relative luminance and
contrast ratio (W3C), Björn Ottosson's OKLab matrices, the modular-scale/fluid-clamp method
known from Utopia, and the Design Tokens Community Group format. iconify-icon-search calls the
public Iconify API (https://api.iconify.design, no key) and reports each icon set's own licence
as the API returns it; icons themselves are not bundled.

## Licence texts

`licenses/` holds the full licence texts referred to above for the agents (which, being single
JSON files, cannot carry a licence file of their own).
