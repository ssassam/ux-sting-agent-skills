# Contributing

Thanks for wanting to improve UX-STING Agent Skills!

## What this is

Agent Skills (open [Agent Skills](https://agentskills.io) format) that teach coding
agents to build accessible, art-directed UI with UX-STING. Licensed **MIT** and
**free to use and contribute to.**

## The one ask: attribution

You may use, fork, modify and redistribute these skills freely under MIT. In
exchange we ask that you:

- **Keep the `LICENSE` and `THIRD_PARTY_NOTICES.md`** with any copy or fork.
- **Credit [VELTEIN](https://veltein.com) and [UX-STING](https://github.com/ssassam/UX-STING)**
  wherever the skills are used or redistributed.

MIT already requires the copyright notice to travel with the software; this just
makes the credit explicit. Some bundled/adapted skills carry their own upstream
MIT notices (e.g. `logo-design`, diagram-design, UI/UX Pro Max) — preserve those
too. See [`THIRD_PARTY_NOTICES.md`](./THIRD_PARTY_NOTICES.md).

## How to contribute

1. **Edit skills only in [`.claude/skills/`](./.claude/skills)** — the single source
   of truth. Do **not** hand-edit the generated mirrors (`.agents/skills/`, `dist/`,
   `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md`,
   `.claude-plugin/*.json`); they are rebuilt.
2. Keep each skill focused on one job. Each `SKILL.md` needs frontmatter `name`
   (must equal the folder) and a concise, front-loaded `description` with trigger
   words.
3. Write consumer-app paths (`@ux-sting/react`, `npx ux-sting …`), not monorepo
   paths (`packages/…`, `pnpm …`) that only exist inside the UX-STING repo.
4. Rebuild the derived artifacts:
   ```bash
   node scripts/build-agent-skills.mjs
   ```
5. Validate the Qoder plugin still passes with the offline validator, and open a PR
   describing the trigger phrases you tested.

## Renaming the repo / changing ownership or credit

All distribution identity lives in the constants at the top of
[`scripts/build-agent-skills.mjs`](./scripts/build-agent-skills.mjs) — `OWNER`,
`REPO_SLUG`, `PLUGIN_ID`, `SITE_URL`, `PROJECT_URL`, `AUTHOR`. Edit them and rebuild;
every pointer file, plugin manifest and install string follows. `REPO_SLUG` must
equal the GitHub repository name.

## Pull request checklist

- [ ] Only `.claude/skills/` edited; artifacts regenerated, not hand-edited
- [ ] `SKILL.md` `name` matches its folder; description has clear triggers
- [ ] Consumer-portable commands only; no monorepo-only paths
- [ ] Attribution and third-party notices preserved
- [ ] `node scripts/build-agent-skills.mjs` runs clean and the Qoder validator passes
