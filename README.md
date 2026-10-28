# Idea Validation Lab

Test your product idea with AI before you build anything. Your AI agent smashes the idea, invents a user, interviews that user, and finally sends you to talk to real people.

## Start

Point your agent at this repo. That is the whole setup:

```
Read https://github.com/mikz0rz/lja-techlab-product-items and start the Idea Validation Lab with me. Follow AGENTS.md.
```

The agent opens the repo and follows [`AGENTS.md`](https://raw.githubusercontent.com/mikz0rz/lja-techlab-product-items/main/AGENTS.md): it fetches the skills, then asks about your idea. Claude Code, Cursor, Codex, Gemini CLI, opencode, Hermes — anything that can open a link will do. You don't type commands or edit files. Just talk.

Agents that want a map of every file first: [`llms.txt`](llms.txt).

**Agent can't open links?** Download the repo (green **Code** button → **Download ZIP**), unzip it, open a terminal inside the folder, and start your agent there (`hermes`, `claude`, `codex`, `gemini`, `opencode`…). The agent reads `AGENTS.md` automatically.

## What happens

```
idea.md → 01-redteam → 02-persona → 03-round-1 → 04-round-2 … → hallway questions → 99-reality-check
 you +     smash the     build the    interview the user,          go ask real         what real people
 agent     idea          user         one round at a time          people              actually said
```

Every step saves a file in `outputs/`. Open them to watch your idea change.

Things you can say along the way:
- "next round"
- "ask the persona: when did you last …?"
- "I disagree with assumption 2"
- "redo step 1"
- "where are we?"
- "start over"

## No terminal? Two other ways

**Option B — nexos.ai workspace agents.** Three ready-made agents, no files and no setup on the student's side: see [`nexos-workspace/`](nexos-workspace/README.md). Same pipeline, same HANDOFF blocks, so a team can switch between the two.

**Option C — a plain chat.** One conversation in any chat:
1. Paste `skills/red-team/SKILL.md` and your idea → copy the HANDOFF block at the end.
2. Paste `skills/proto-persona/SKILL.md` + `template.md` + that HANDOFF → copy the persona.
3. Paste `skills/interview-loop/SKILL.md` + the persona + the `top_assumptions` → type "next round" until it says `EXHAUSTED`.

## How it works

- The repo URL is the entry point. `AGENTS.md` tells the agent how to fetch the repo when it has no files yet; `llms.txt` is the file map for agents that look for one.
- `AGENTS.md` is the coach. Most agents read it automatically (`CLAUDE.md` and `GEMINI.md` point to it).
- `skills/` holds three skills. Each one ends with a **HANDOFF** block in a fixed format, and the next skill reads it. Skills connect through contracts, not magic.
- `nexos-workspace/` holds the same three steps as three separate nexos.ai workspace agents, for teams that don't want a terminal.

---

## For the presenter

- Demo with the sample idea: say "use the sample idea" (`examples/sample-idea.md`).
- Rehearse the full run 3–5 times. Keep the best `01`–`03` (and a backup `04-round-2.md`) in `examples/`, not in `outputs/`.
- Tune by changing a skill and rerunning. Never hand-edit outputs.
- Test the live round with 3–4 likely audience questions, including "Would you use it?".
- Multi-model check: paste the same `02-persona.md` and question into two different models side by side. Where they differ, the model is talking, not the user. Look for `[NEW—MODEL INVENTED]`.
- Screen: `outputs/` on the left, agent on the right, font 20+, notifications off.
- Before sharing the repo: `outputs/` should contain only `.gitkeep`, and `idea.md` should be the EMPTY template.
- If the repo moves, update the URL in three places: `README.md` (Start), `AGENTS.md` (bootstrap section) and `llms.txt`.
