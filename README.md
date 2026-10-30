# UX-STING Agent Skills

> **⚠️ Moved — this repo is archived.** The skills now live in the single, SEO-indexed
> home [**ssassam/UX-STING**](https://github.com/ssassam/UX-STING). Install from there:
> `npx skills add ssassam/UX-STING` · or in Claude Code
> `/plugin marketplace add ssassam/UX-STING` → `/plugin install ux-sting@ux-sting`.

[![npm: ux-sting](https://img.shields.io/npm/v/ux-sting.svg?label=ux-sting)](https://www.npmjs.com/package/ux-sting)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![8+1](https://img.shields.io/badge/skills-8%20%C3%97%201%20agent-7c5cff.svg)](#skills)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-plugin-blue.svg)](#install)
[![Codex](https://img.shields.io/badge/Codex-skills-blueviolet.svg)](#install)
[![Cursor](https://img.shields.io/badge/Cursor-skills-lightgrey.svg)](#install)
[![VS%20Code](https://img.shields.io/badge/VS%20Code-Copilot-2b81c9.svg)](#install)
[![Gemini](https://img.shields.io/badge/Gemini-CLI-4285F4.svg)](#install)
[![Qoder](https://img.shields.io/badge/Qoder-plugin-ff5c8a.svg)](#install)

Cross-host **Agent Skills** that teach coding agents to build accessible, themeable,
art-directed UI with [UX-STING](https://github.com/ssassam/UX-STING), an MIT React
design system for Next.js and any React app.

One source of truth — [`.claude/skills/`](./.claude/skills) — generates pointer files
and distributable bundles for every major agent platform.

## Skills

| Skill | What it does |
| --- | --- |
| **ux-sting-design-agent** | Universal design agent — routes any UI task to the right skill and always verifies |
| **ux-sting** | Pick components, apply tokens/themes, wire `@ux-sting/react` into an app |
| **ux-sting-taste** | Art-direct a page so it looks designed for the client, not generated |
| **ux-sting-review** | Accessibility/UX/design review with evidence and severity ranking |
| **ux-sting-explore** | Explore three real directions side by side, then converge |
| **ux-sting-universal** | Reference → Design DNA → page → browser QA → improved page |
| **ux-sting-3d** | Accessible, on-theme three.js / shader moments |
| **ux-sting-diagrams** | On-theme editorial diagrams via the diagram-design skill |
| **logo-design** | Logo / brand-mark from brief to production files (vendored, MIT) |

## Works with

The `SKILL.md` folders follow the open [Agent Skills](https://agentskills.io) format,
so the same skills load in **Claude Code, Cursor, Codex, GitHub Copilot / VS Code,
Gemini CLI, Qoder** and other compatible hosts.

## Install

**Universal (recommended):**

```bash
npx skills add ssassam/ux-sting-agent-skills
```

This detects your agent and installs the skills into the right place. The tools the
skills drive are on npm too — `npm i -D ux-sting @ux-sting/qa @ux-sting/extract @ux-sting/images`
([`ux-sting` on npm](https://www.npmjs.com/package/ux-sting), currently `0.6.2`). Pointer files
([`AGENTS.md`](./AGENTS.md), [`CLAUDE.md`](./CLAUDE.md), [`GEMINI.md`](./GEMINI.md),
[`.github/copilot-instructions.md`](./.github/copilot-instructions.md)) make the
skills discoverable to hosts that read a repo context file.

**Claude Code (native plugin):** this repo is also a Claude Code marketplace —

```text
/plugin marketplace add ssassam/ux-sting-agent-skills
/plugin install ux-sting@ux-sting-agent-skills
```

(`.claude-plugin/plugin.json` + `.claude-plugin/marketplace.json`, pointing at the
same `.claude/skills/` — no duplicate copy.)

**OpenAI Codex:** Codex has no separate plugin manifest — it scans the open skills
standard directly. This repo ships a generated [`.agents/skills/`](./.agents/skills)
mirror of `.claude/skills/` that Codex auto-discovers from the repo root. Open Codex
in this repo and run `/skills`, or invoke one with `$ux-sting-taste`. You can also
pull them anywhere with `npx skills add ssassam/ux-sting-agent-skills`.

**Qoder:** load the generated plugin at [`dist/ux-sting-agent-skills/`](./dist/ux-sting-agent-skills)
(validated against the Qoder plugin manifest).

**Manual:** copy any folders from [`.claude/skills/`](./.claude/skills) into your
host's skills directory.

**Offline / prebuilt:** download the Qoder plugin and skills-bundle zips from
[Releases](https://github.com/ssassam/ux-sting-agent-skills/releases/latest).

## Runtime dependencies (not bundled)

The skills are instructions — they call tools the user installs:

- `@ux-sting/react` + React 18/19 + Tailwind CSS 4 (UI skills)
- `npm i -D ux-sting @ux-sting/qa @ux-sting/extract @ux-sting/images` and
  `npx playwright-core install chromium` — for `ux-sting qa | extract | theme | images | dna`
- Python 3 (standard library only) for the `logo-design` scripts

## Build

```bash
node scripts/build-agent-skills.mjs   # regenerate pointers + dist bundles + Qoder plugin
pwsh scripts/zip-dist.ps1             # zip the dist outputs
```

Edit skills in [`.claude/skills/`](./.claude/skills) only; everything else is generated.
To rename the repo or change owner/credit, edit the constants at the top of
[`scripts/build-agent-skills.mjs`](./scripts/build-agent-skills.mjs) (`OWNER`, `REPO_SLUG`,
`SITE_URL`, `PROJECT_URL`) and rebuild — every pointer, manifest and install string follows.

## Provenance, credit & license

MIT — see [`LICENSE`](./LICENSE). **Free to use and to contribute.** In exchange we
ask that you keep the license notice and **credit [VELTEIN](https://veltein.com) and
[UX-STING](https://github.com/ssassam/UX-STING)** where these skills are used,
forked or redistributed.

These skills adapt and vendor third-party work (UI/UX Pro Max, taste-skill,
design-taste, diagram-design, logo-design-skill, three.js guidance). Full
attribution and license obligations are in
[`THIRD_PARTY_NOTICES.md`](./THIRD_PARTY_NOTICES.md) and must travel with any
redistribution. See [`CONTRIBUTING.md`](./CONTRIBUTING.md) to contribute.

## Made by VELTEIN

UX-STING Agent Skills by [Issam El Bani — VELTEIN](https://veltein.com). Support the
work on Buy Me a Coffee.
