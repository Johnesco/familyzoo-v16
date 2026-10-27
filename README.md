# Family Zoo — v16: After Hours & First-Time Text

The zoo closes. A story state flips, the zookeeper leaves, and once he is gone each animal tells you what it really thinks when you visit it. The parrot's flavour line cycles, and the plaque's aside is printed only the first time — both written in Chord.

Step 16 of sixteen in the [Family Zoo](https://github.com/Johnesco/familyzoo) tutorial for [Chord](https://sharpee.net/chord/), the authoring language of the [Sharpee](https://sharpee.net) interactive fiction engine.

## What this step adds

- `states: open, after-hours` in the header
- `while after-hours` on clauses and descriptions
- `define sequence closing time` driving the transition
- Conditions joined with `and`: `while after-hours and the zookeeper is in the Staff Parking Lot`
- `, once` on a clause, so a confession is heard one time
- `define phrase aside, first-time` beside `define phrase flavor, cycling`, used as `{flavor} {aside}` in a description

## The source

The whole step is one file: [`familyzoo-v16.story`](./familyzoo-v16.story) — the step before it plus the ideas above. The chapter that walks through it is [`docs/v16-after-hours-first-time-text.md`](./docs/v16-after-hours-first-time-text.md).

## Playing and testing

```bash
npx sharpee play
npx sharpee test          # replays familyzoo-v16.tests/
python ../tools/build.py familyzoo-v16 --force
```

## Engine

Pinned in `package.json`, held across the whole `@sharpee/*` scope by an `overrides` block.

The 0.9.x TypeScript edition this replaced is kept in [`legacy/`](./legacy).
