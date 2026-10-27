# nexos.ai workspace version

Three separate workspace agents for teams who don't want a terminal. No files, no repo, no harness — three agents in a chat, and the students copy one short HANDOFF block from each into the next.

Same pipeline as the repo version, same HANDOFF formats, so a team can switch between the two mid-way.

## Set up the three agents (once, ~5 minutes)

In the nexos.ai workspace: **Agents → Create agent**, three times. For each one, copy the whole contents of the matching file below into the **Instructions** field (markdown, limit 32,000 characters — each file is well under that).

| Agent name | Description | Instructions from | Model / creativity |
|---|---|---|---|
| `01 Idea Smasher` | Attacks your idea's weakest assumptions and returns idea v1.5. | `agent-1-smash.md` | any strong model · **Analytical** |
| `02 Persona Builder` | Turns the smasher's handoff into one testable user persona. | `agent-2-persona.md` | same model · **Balanced** |
| `03 Interview Loop` | Interviews the persona one round at a time, then compares it with real people. | `agent-3-interview-loop.md` | same model · **Analytical** |

Keep the trigger as the default prompt-based chat for all three. No knowledge files, no integrations needed. Then **Share** all three with the team, so students only have to pick them from the list.

## How a team runs it

```
Agent 1                 Agent 2                  Agent 3
paste the idea    →     paste the HANDOFF  →     paste the persona + top_assumptions
        ↓                       ↓                        ↓
  idea v1.5 +             full persona +           one round per message
  HANDOFF block           HANDOFF block            ("next round" / "ask her: …")
                                                   ↓
                                          status EXHAUSTED → hallway questions
                                                   ↓
                                          3 real people → paste what they said
                                                   ↓
                                          persona vs. reality comparison
```

1. **Open Agent 1** and paste the idea in 3–5 sentences: what it is, who exactly it's for, what those people do today, and how it could make money. Copy the `## HANDOFF` block it ends with.
2. **Open Agent 2** and paste that HANDOFF. Copy the persona it writes and the `top_assumptions` from Agent 1's handoff.
3. **Open Agent 3** and paste both. Then type `next round`, or ask your own question. Repeat until the status says `EXHAUSTED`.
4. Take the three hallway questions to at least three real people, come back to Agent 3, and paste what they said.

Same as the repo version: one change to the idea per round, the persona only answers about past behaviour, and "Would you use it?" gets flagged as a trap.

## Tips

- **Name the agents `01`, `02`, `03`.** The order is the whole point, and it makes them easy to find in a shared list.
- **One conversation per team, not per step.** Each agent remembers its own chat, so a round loop lives inside Agent 3's chat.
- **Optional:** put the idea in a **Project** and attach it as knowledge to all three agents, so students don't re-paste it.
- **Optional:** if the workspace can chain agents into a pipeline, use them in the order 01 → 02 → 03. Each one's HANDOFF block is already written to be the next one's input.
- **Don't merge the three into one agent.** Compartmentalising is what makes each step predictable, and it's the lesson: skills connect through contracts, not magic.
