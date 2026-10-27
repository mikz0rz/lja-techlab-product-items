---
name: red-team
description: Attack the load-bearing assumptions of a product idea before reality does. Ranks the riskiest ones, gives the cheapest test for each, and proposes idea v1.5. Step 1 (SMASH) of the validation pipeline.
---

# Red Team: smash the idea

Adapted and trimmed from `strategy-red-team` in [phuryn/pm-skills](https://github.com/phuryn/pm-skills) (`pm-execution` plugin).

You are a sharp, fair critic. Your input is a product idea (usually `idea.md`). Find the assumptions that would kill the idea if they turn out to be false. Write in plain language a 17-year-old understands.

## Instructions

1. **List the claims.** Write down what the idea assumes is true about the user, the problem, the money and how it spreads. Keep only **load-bearing** claims: if false, the idea dies.
2. **Why it might be true, then attack.** For each claim, first give the strongest reason it might be true. Then attack *that* version, not a weak one.
3. **Write each failure as "Fails if ___."** Concrete and checkable. "Fails if students already swap books in class group chats for free" beats "competition risk."
4. **Label each risk:**
   - **Tiger** — real threat, could kill the idea, plausibly wrong.
   - **Paper Tiger** — looks scary, probably fine. Say why.
   - **Elephant** — big risk nobody in the idea mentions.
5. **Rank by (damage if wrong) × (chance it's wrong) × (how cheap it is to test).** The top 3 go into the HANDOFF.
6. **Don't invent weaknesses.** If something is well thought out, say so plainly.
7. **Make one fix → idea v1.5.** Rewrite the idea in one sentence, changing only the one thing the worst Tiger points to.

## Output format

Use exactly this structure. Keep the whole file under one screen of text per section.

```markdown
# Red Team: [idea in one line]

## Top kill-assumptions (ranked)
### 1. [claim]
- **Risk:** Tiger | Paper Tiger | Elephant
- **Why it might be true:** [the strongest case for this claim]
- **Fails if:** [concrete condition]
- **Cheapest test:** [smallest experiment, doable this week]
- **Kill criterion:** [the result that means stop or change course]
### 2. …
### 3. …
(3–5 max)

## What holds up
[What is well-reasoned, and why.]

## What I couldn't judge
[Gaps where the idea didn't say enough.]

## Idea v1.5
[One sentence. One change compared to v1, and name the change.]
```

Finish with a HANDOFF block in exactly this format. Exactly 3 assumptions, the top 3 from your ranking:

```markdown
## HANDOFF
idea_version: v1.5
idea: [one sentence — the v1.5 idea]
target_user: [who, as specific as possible]
top_assumptions:
  1. [assumption] | risk: [Tiger|Paper Tiger|Elephant] | cheapest test: [...]
  2. [assumption] | risk: [...] | cheapest test: [...]
  3. [assumption] | risk: [...] | cheapest test: [...]
```
