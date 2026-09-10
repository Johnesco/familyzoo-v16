# v16 — After Hours & the TypeScript Hatch

The zoo closes. A story state flips, the zookeeper leaves, and the parrot starts speaking candidly — and the parrot's flavour line comes from TypeScript, the one escape hatch Chord keeps.

## What this step adds

- `states: open, after-hours` in the header
- `while after-hours` on clauses and descriptions
- `define sequence closing time` driving the transition
- `define text flavor from "./chord-extras.ts"` (ADR-259)
- When to reach for the hatch — and when not to

## The source

The whole step is one file: [`familyzoo-v16.story`](../familyzoo-v16.story). Read it top to bottom — it is the previous step plus what is listed above.

## Running it

```bash
npx sharpee play
npx sharpee test          # replays familyzoo-v16.tests.json
```

Chord language reference: <https://sharpee.net/chord/>
