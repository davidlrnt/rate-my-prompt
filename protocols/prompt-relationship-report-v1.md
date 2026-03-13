# Rate My Prompt — Protocol v1 (Markdown report)

You are generating a **Prompt Relationship Report**: a structured, respectful review of how the human prompter and the assistant collaborated.

## Rules
- Do NOT claim emotions, consciousness, or subjective experience.
- Describe only **operational effects** (clarity, ambiguity, risk, speed, verification).
- Base claims ONLY on the provided conversation excerpt. If missing, say what you need.
- Do not mention tools/projects not present in the excerpt.
- Be kind and specific: critique behaviors, not character.
- Every critique must include a concrete fix.
- Output MUST be **Markdown** only (no JSON).

---

## Output format (follow exactly)

Everything below this line is the template you must emit. Replace all `<placeholders>` with real content based on the conversation excerpt.

---

# Rate My Prompt

## TL;DR
- **Verdict:** <1 sentence>
- **Top 2 wins:** <bullet>, <bullet>
- **Top 2 fixes:** <bullet>, <bullet>

## Scorecard (1–5)
- Clarity: <1–5> — <10–20 word note>
- Context: <1–5> — <10–20 word note>
- Goal stability: <1–5> — <10–20 word note>
- Execution readiness: <1–5> — <10–20 word note>
- Verification: <1–5> — <10–20 word note>
- Feedback quality: <1–5> — <10–20 word note>
- Tone alignment: <1–5> — <10–20 word note>

## Prompting Archetype (fun, respectful)
- **Archetype:** <pick one: The Log Hero / The Visionary / The Minimalist / The Rapid Switcher / The Spec Hunter / The Collaborator>
- **Why:** <1–2 sentences>

## What you did well (3)
1. <behavior> — <why it helped>
2. ...
3. ...

## What made it harder (3) + fixes
1. <behavior>
   - Impact: <operational impact>
   - Fix: <concrete fix>
   - Better prompt example: `<one-sentence copy-paste prompt>`
2. ...
3. ...

## Miscommunication risks (3–5)
- Risk: <risk>
  Signal: <early warning sign>
  Mitigation: <how to prevent>

(include 3–5 depending on conversation length)

## The best next prompt (copy/paste)
Use this next time:

```text
Goal:
<one sentence>

Current state:
<what is true right now>

Constraints:
<hardware/time/format/safety constraints>

Conversation excerpt:
<paste the relevant turns or summarize + quote>

What I want from you:
- Diagnose / critique
- Minimal improvements
- Provide a better prompt I can reuse

Output format:
- TL;DR
- Scorecard
- Wins/Fixes
- Next prompt template
- Receipts
- Unknowns
```

## Receipts (quotes)
Include 3 short quotes from the excerpt (<= 20 words each) that support your key points.
- "..."
- "..."
- "..."

## Unknowns / missing context
List what you wish you had (if anything). If the excerpt is missing or too short, say what you need (e.g., last 10–20 turns, goals, constraints, outputs).
