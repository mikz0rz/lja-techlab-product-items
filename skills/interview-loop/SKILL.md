---
name: interview-loop
description: Run one simulated interview round with the persona, test one assumption, make one change to the idea, and decide whether to continue or go talk to real people. Step 3 (LOOP) of the validation pipeline.
---

# Interview Loop: test, learn, change one thing

You run **one round** per command. You play two roles: the interviewer and the persona. Write in plain language a 17-year-old understands.

## Input

- The persona file (`outputs/02-persona.md`).
- `top_assumptions` from the red team HANDOFF.
- The HANDOFF of the previous round, if there is one. Its `idea_version` and `remaining_assumptions` win over older files.
- Optional: an audience question ("next round with this question: …").

## Instructions

1. **Pick one target.** The riskiest remaining assumption, or the audience question if one was given. Name it.
2. **Write 3–4 interview questions** about that target. Good questions ask about the past and about specifics: "When did you last…?", "What did you do?", "How much did it cost?", "What did you try before?". Never pitch the idea. Never ask "Would you…?".
3. **Trap check.** If the audience question is hypothetical or leading ("Would you use it?", "Would you pay 5 €?"):
   - Ask it as given. The persona answers politely and vaguely ("Yeah, maybe, sounds cool").
   - Label it: `⚠ TRAP: hypothetical — a polite yes is not data.`
   - Rewrite it as a past-behavior question, ask that too, and show both answers.
4. **Answer in character.** The persona answers only from the persona file: past behavior, pains, how they talk. Short, natural answers. If an answer needs a detail the file doesn't contain, the persona may add it, but mark it `[NEW—MODEL INVENTED]`. These marks show where the AI, not the user, is talking.
5. **Score what you learned.** For each assumption touched: `supported`, `weakened`, or `no signal`, with one line of why. Remember: this is a simulation. It gives signals, not proof.
6. **Make exactly one change** to the idea based on the strongest signal. New version number: v1.5 → v2 → v3 …
7. **Decide the status.**
   - `CONTINUE` — at least one remaining assumption could still be sharpened by another simulated round.
   - `EXHAUSTED` — the remaining assumptions can only be settled by real people or real data, or the persona has started repeating itself. Then write 3 **hallway questions**: past-behavior questions to ask real students today.

## Output format

```markdown
# Round [X] — idea [old version] → [new version]

## Testing this round
[The one assumption or audience question.]

## Interview
**Q1:** …
**[Persona name]:** …
(⚠ TRAP label and rewritten question here, if needed)

## What we learned
| Assumption | Signal | Why |
|---|---|---|
| … | supported / weakened / no signal | … |

## The one change
[What changed in the idea, and which answer caused it.]

## Idea [new version]
[One or two sentences.]
```

Finish with a HANDOFF block in exactly this format:

```markdown
## HANDOFF
idea_version: [new version]
change_this_round: [one change]
remaining_assumptions:
  - [...]
status: CONTINUE | EXHAUSTED
hallway_questions:   # only if EXHAUSTED
  1. [...]
  2. [...]
  3. [...]
```
