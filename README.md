# Family Zoo — v16: After Hours & the TypeScript Hatch

The zoo closes. A story state flips, the zookeeper leaves, and the parrot starts speaking candidly — and the parrot's flavour line comes from TypeScript, the one escape hatch Chord keeps.

Step 16 of sixteen in the [Family Zoo](https://github.com/Johnesco/familyzoo) tutorial for [Chord](https://sharpee.net/chord/), the authoring language of the [Sharpee](https://sharpee.net) interactive fiction engine.

## What this step adds

- `states: open, after-hours` in the header
- `while after-hours` on clauses and descriptions
- `define sequence closing time` driving the transition
- `define text flavor from "./chord-extras.ts"` (ADR-259)
- When to reach for the hatch — and when not to

## The source

The whole step is one file: [`familyzoo-v16.story`](./familyzoo-v16.story) — the step before it plus the ideas above. The chapter that walks through it is [`docs/v16-after-hours-the-typescript-hatch.md`](./docs/v16-after-hours-the-typescript-hatch.md).

## Playing and testing

```bash
npx sharpee play
npx sharpee test          # replays familyzoo-v16.tests.json
python ../tools/build.py familyzoo-v16 --force
```

## Engine

Pinned to `@sharpee/*` **5.3.0** (Chord 3.6.0), held there by an `overrides` block: 5.3.1 publishes broken subpath exports and breaks `sharpee test`.

The 0.9.x TypeScript edition this replaced is kept in [`legacy/`](./legacy).
