# Family Zoo — v16 — Scoring and Endgame — Claude Project Memory

> Project-specific context for Claude Code sessions in this folder. Shared context
> (toolchain, commands, testing standard, conventions) comes from the workspace
> `CLAUDE.md` one level up, which Claude Code loads automatically. Do not restate
> it here; link to it.

<!-- workspace: ../CLAUDE.md -->

## Project Identity

**Name:** Family Zoo — v16 — Scoring and Endgame
**Purpose:** Sharpee tutorial step 16 — Scoring and Endgame.
**Engine:** Sharpee, the 0.9.x TypeScript pipeline (pinned in `package.json` in the
authoring repo — this folder ships built output only).
**Repository:** https://github.com/Johnesco/familyzoo-v16
**Live:** https://johnesco.github.io/familyzoo-v16/

## Project Context

This folder is a **frozen** tutorial step in the Family Zoo group (`versionOf = familyzoo`).

Family Zoo is a 17-step progressive tutorial for the Sharpee TypeScript engine. Each
step adds one chapter of the story and one slice of the engine. The steps are published
as separate repos so the hub can show the whole trail; the model is
[`multi-version-guide.md`](https://github.com/Johnesco/ifhub/blob/main/reference/multi-version-guide.md).

## Key Design Decisions (do not change without discussion)

- **Frozen.** This step is published history. Do not add features. The cascade rule from the
  multi-version guide applies: a fix in vN propagates *upward* to v(N+1)… and Current,
  never downward.
- **Stays on the 0.9.x TypeScript pipeline.** The tutorial teaches that API. Translating
  it to Chord would delete the thing it exists to explain.
- **Built output is the artifact.** `play.html`, the bundle, `source.html`, `tests.html`
  and the walkthrough files are committed and served by GitHub Pages.

## File Structure Overview

```
familyzoo-v16/
├── CLAUDE.md              THIS FILE
├── README.md              public documentation
├── ifhub.conf             the IF Hub card + version grouping
├── play.html              the player (loads styles.css + the bundle + theme-listener.js)
├── familyzoo-16.js         the built story bundle
├── source.html            multi-file source view (sourceBrowser = yes)
├── tests.html             the test report
├── walkthrough.txt        + walkthrough_output.txt, walkthrough-guide.txt
├── src/                   the TypeScript this step is built from
├── docs/                  the tutorial chapter for this step
└── tests/transcripts/     the transcript this step's walkthrough replays
```

## Working in this project

**SDLC profile:** core

Shared rules live in the workspace `../CLAUDE.md` (loaded automatically). Build and ship:

```bash
python ../tools/build.py familyzoo-v16
python C:/code/ifhub/tools/ship.py familyzoo-v16
```

This project uses the [sdlc-baseline](https://github.com/Johnesco/sdlc-baseline) universal
workflow. Claude must follow these canonical docs:

- [Workflow (7 steps)](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/workflow.md)
- [Roles & hat-switch protocol](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/roles.md)
- [Definition of Done](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/definition-of-done.md)
- [Severity & priority matrix](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/severity-matrix.md)
- [Commit, PR, and branch conventions](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/commit-conventions.md)
- [Release management](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/release-management.md)
- [Testing](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/testing.md)
- [Backlog hygiene](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/backlog-hygiene.md)
- [ADR protocol](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/adrs.md)
- [Profiles](https://github.com/Johnesco/sdlc-baseline/blob/main/docs/profiles.md)

**Three non-negotiables:**

1. **No code without a ticket.** An Issue, or an ADR stub for a decision.
2. **Decide before you build.** Anything above a tuning tweak gets a six-line ADR stub first.
3. **Claude cannot QA its own work.** The Verify column is always human-owned.

### Project-specific deviations

Split out of the familyzoo monorepo on 2026-09-10 so each tutorial step could be its own
hub entry. The authoring tree for all 17 steps stays in `familyzoo/`.

## Project History

### Recent Changes
- 2026-09-10: Split from the familyzoo monorepo into a per-version repo.
