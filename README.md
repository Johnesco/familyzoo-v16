# Family Zoo — v16 — Scoring and Endgame

Turns the zoo into a 75-point game with an ending: visit rooms, feed animals, and collect items to win. Introduces the score ledger, unique award IDs, and a victory daemon that watches for the win condition.

Step 16 of the [Family Zoo](https://github.com/Johnesco/familyzoo) tutorial — a progressive walkthrough of the [Sharpee](https://sharpee.net) TypeScript interactive fiction engine, from a single room to a full multi-file story.

## What this step teaches

- world.setMaxScore and world.awardScore with idempotent unique IDs
- world.getScore and the built-in score command
- Chained event handlers awarding points on room entry
- A high-priority victory daemon driving endgame state flags
- Designing a balanced scoring table across exploration and action

## Playing

Open `play.html`, or preview the folder:

```bash
python -m http.server 8000 --directory familyzoo-v16
```

## Building

This is a **frozen 0.9.x TypeScript version**. The built player in this folder is the published artifact; it is re-laid from `browser/` by the workspace build:

```bash
python ../tools/build.py familyzoo-v16
python C:/code/ifhub/tools/ship.py familyzoo-v16
```

The authoring tree for every version lives in the [familyzoo](https://github.com/Johnesco/familyzoo) repo.
