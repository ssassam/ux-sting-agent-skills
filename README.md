# UX-STING Agent Skills

Cross-host **Agent Skills** that teach coding agents to build accessible, themeable,
art-directed UI with [UX-STING](https://github.com/ssassam/UX-STING), an MIT React
design system for Next.js and any React app.

One source of truth — [`.claude/skills/`](./.claude/skills) — generates pointer files
and distributable bundles for every major agent platform.

## Skills

| Skill | What it does |
| --- | --- |
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

This detects your agent and installs the skills into the right place. Pointer files
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

## Provenance & license

MIT — see [`LICENSE`](./LICENSE). These skills adapt and vendor third-party work
(UI/UX Pro Max, taste-skill, design-taste, diagram-design, logo-design-skill, three.js
guidance). Full attribution and license obligations are in
[`THIRD_PARTY_NOTICES.md`](./THIRD_PARTY_NOTICES.md) and must travel with any
redistribution.

## Made by VELTEIN

UX-STING by [Issam El Bani](https://github.com/ssassam) — support the work on Buy Me a Coffee.
