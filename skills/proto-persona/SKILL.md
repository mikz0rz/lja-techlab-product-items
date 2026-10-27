---
name: proto-persona
description: Turn the red team's HANDOFF into one assumption-based persona that can be interviewed. Every unproven detail is tagged so it can be tested. Step 2 (PERSONA) of the validation pipeline.
---

# Proto-Persona: give the user a face

Adapted and trimmed from [deanpeters/proto-persona](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/proto-persona/SKILL.md).

A proto-persona is a **hypothesis**, not research. It is a best guess about one real-feeling user, written so every guess is visible and can be tested. Write in plain language a 17-year-old understands.

## Input

The red team HANDOFF: `idea`, `target_user`, `top_assumptions`. Nothing else is needed.

## Instructions

1. **One persona only.** Build the `target_user` from the HANDOFF. Not a mix of several users.
2. **Name.** A realistic first name for the user's country (e.g. "Gabija" for a Lithuanian student). Not "User 1".
3. **Behavior over demographics.** "16, lives in Kaunas" says nothing. "Buys books in August at the last minute, asks her cousin first" explains choices.
4. **Fill `template.md`** (in this folder), section by section. Keep each bullet to one line.
5. **Past behavior is the most important section.** Write 3–5 concrete things this person *did* the last time they had the problem. The interview loop uses only these to answer questions.
6. **Tag every guess.** Anything not stated in the idea or HANDOFF gets `[ASSUMPTION—VALIDATE]`. Each of the 3 `top_assumptions` must show up in the persona at least once as a tagged line.
7. **Quotes are invented, so say so.** Write 2–3 quotes that show mindset, not marketing ("I just want it cheap and not weird" — yes; "I love delightful apps!" — no). Mark each `[INVENTED]`.
8. **No fake certainty.** If you don't know something, write the gap instead of making it up.

## Output format

The filled `template.md`, then a HANDOFF block in exactly this format:

```markdown
## HANDOFF
persona_name: [name]
persona_file: outputs/02-persona.md
open_assumptions:
  - [each line tagged [ASSUMPTION—VALIDATE], copied short]
  - ...
```
