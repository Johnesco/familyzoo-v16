# Family Zoo — v16 — After Hours & Story States — Claude Project Memory

> Project-specific context for Claude Code sessions in this folder. Shared context
> (toolchain, commands, testing standard, conventions) comes from the workspace
> `CLAUDE.md` one level up, which Claude Code loads automatically. Do not restate
> it here; link to it.

<!-- workspace: ../CLAUDE.md -->

## Project Identity

**Name:** Family Zoo — v16 — After Hours & Story States
**Purpose:** Step 16 of sixteen in the Family Zoo tutorial for Chord, the Sharpee
authoring language.
**Engine:** Sharpee / Chord. The exact version is pinned in `package.json`, held across
the whole `@sharpee/*` scope by an `overrides` block; the workspace `CLAUDE.md` is the one
home for which version that is.
**Repository:** https://github.com/Johnesco/familyzoo-v16
**Live:** https://johnesco.github.io/familyzoo-v16/

## Project Context

This folder is a **frozen** step in the Family Zoo group (`versionOf = familyzoo`). The
group's master story, its ticket tracker and the group landing page live in
[`familyzoo`](https://github.com/Johnesco/familyzoo); this step's place in the trail is at
https://johnesco.github.io/familyzoo/#familyzoo-v16.

Family Zoo builds one game across sixteen steps, v01 (one room) to v16 (the whole zoo).
Each step is its own repo so the hub can show the whole trail; the model is
[`multi-version-guide.md`](https://github.com/Johnesco/ifhub/blob/main/reference/multi-version-guide.md).

## Key Design Decisions (do not change without discussion)

- **Frozen.** This step is published history. Do not add features. The cascade rule from the
  multi-version guide applies: a fix in vN propagates *upward* to v(N+1) … v16 and the
  master, never downward.
- **Cumulative, edited in place.** `familyzoo-v16.story` is the step before it plus one
  idea. There is no slicing tool or step map: a change is made here and in every later step
  by hand, and v16's body must stay identical to the master's.
- **A step's title lives in six places.** The `.story` header, the opening test card,
  `ifhub.conf`, `README.md`, and the master's `README.md` and `landing.json`.
- **Chord, not TypeScript.** Reworked from the 0.9.x TypeScript edition on 2026-09-10; the
  old edition, including its tutorial chapters, is kept in `legacy/`.
- **Built output is the artifact.** `play.html`, `game.js`, `tests.html` and the
  walkthrough files are committed and served by GitHub Pages.

## File Structure Overview

```
familyzoo-v16/
├── CLAUDE.md                  THIS FILE
├── README.md                  public documentation
├── ifhub.conf                 the IF Hub card + version grouping
├── familyzoo-v16.story        the step's story
├── familyzoo-v16.tests/       the tests document (segmented, one file per line)
├── familyzoo-v16.config.json  IFID and config
├── play.html, game.js         the built player
├── tests.html                 the test report
├── walkthrough.txt            the full-coverage walkthrough, its coverage marker,
│                              its captured output and the guide
├── src/browser-entry.ts       browser entry, regenerated from the devkit template
└── legacy/                    the 0.9.x TypeScript edition of this step
```

## Working in this project

**SDLC profile:** core

Shared rules live in the workspace `../CLAUDE.md` (loaded automatically). Build and ship:

```bash
python ../tools/build.py familyzoo-v16 --force
python C:/code/ifhub/tools/ship.py familyzoo-v16
```

`build.py` keeps a full-coverage walkthrough as it is, so after a story or engine change
re-capture `walkthrough_output.txt` by replaying `walkthrough.txt` through
`npx sharpee play` (drop its four-line banner).

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

## Project History

### Recent Changes
- 2026-10-28: This file rewritten for the Chord layout; walkthrough transcript
  re-captured (familyzoo#13).
- 2026-10-27: Moved to the Chord 4 engine and rebuilt (familyzoo#12).
- 2026-09-10: Split from the familyzoo monorepo into a per-version repo; Chord edition
  replaced the TypeScript one.
