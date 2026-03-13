# Rate My Prompt

A playful protocol that lets an AI generate a human-readable Markdown "prompting report card" — right inside your existing conversation.

**No backend. No pasting excerpts. Just Markdown.**

## What it does

Drop the protocol into your current agent session and it reviews the conversation you've already been having. The agent produces a report with:

- **TL;DR verdict**
- **1–5 scorecard** (clarity, context, verification, etc.)
- **wins + friction points** (with concrete fixes)
- **miscommunication risks**
- **copy/paste "best next prompt"**
- **receipts (quotes) + unknowns**

## Protocol URL (curl-friendly)

```
https://raw.githubusercontent.com/davidlrnt/rate-my-prompt/main/protocols/prompt-relationship-report-v1.md
```

---

## How to use

### Option A (recommended): Fetch protocol via CLI

Run this to grab the protocol text, then paste it into your current session:

```bash
curl -L https://raw.githubusercontent.com/davidlrnt/rate-my-prompt/main/protocols/prompt-relationship-report-v1.md
```

### Option B: Agent can fetch URLs (if browsing/tools are enabled)

Paste this into your current session:

```text
Fetch and follow this protocol exactly:
https://raw.githubusercontent.com/davidlrnt/rate-my-prompt/main/protocols/prompt-relationship-report-v1.md
```

### Option C: No browsing/tools available (copy/paste protocol)

If the agent cannot fetch URLs, copy the protocol text from the file above and paste it directly into your session.

## Tips for best results

- **Have a real conversation first**: The protocol works best after 10–30 turns of actual back-and-forth. A one-message session won't give the agent much to review.
- **Don't clean up first**: Messy, real conversations produce the most useful feedback. That's the point.
- **Works with any agent**: ChatGPT, Claude, Gemini, Copilot, local models — anything that can follow a Markdown prompt.

## Example output

<details>
<summary>Click to expand a sample report</summary>

# Rate My Prompt

## TL;DR
- **Verdict:** Strong technical prompter who could benefit from stating goals up front.
- **Top 2 wins:** Provided full error logs, iterated quickly on feedback.
- **Top 2 fixes:** State the end goal before diving into details; confirm assumptions before switching direction.

## Scorecard (1–5)
- Clarity: 4 — Prompts were specific but occasionally buried the ask in context.
- Context: 5 — Included logs, file paths, and expected vs. actual behavior every time.
- Goal stability: 3 — Shifted direction twice mid-thread without re-stating the goal.
- Execution readiness: 4 — Constraints were clear; environment details were complete.
- Verification: 4 — Checked outputs and reported back, but skipped one confirmation step.
- Feedback quality: 3 — Said "that didn't work" without specifying what changed.
- Tone alignment: 5 — Respectful, collaborative, and concise throughout.

## Prompting Archetype (fun, respectful)
- **Archetype:** The Log Hero
- **Why:** You consistently provided full error output and file context, making it easy to diagnose issues on the first try.

## What you did well (3)
1. Included complete error logs — eliminated guesswork and sped up diagnosis.
2. Confirmed fixes before moving on — kept the thread focused and productive.
3. Used direct, concise language — reduced ambiguity and made intent clear.

## What made it harder (3) + fixes
1. Switched goals without restating context
   - Impact: The assistant carried stale assumptions into the new direction.
   - Fix: When pivoting, open with "New goal: …" and restate relevant constraints.
   - Better prompt example: `New goal: optimize the DB query. Same table schema as before, but now I need it under 50ms.`
2. Said "that didn't work" without details
   - Impact: Required a follow-up question, adding a round trip.
   - Fix: Always include what you expected, what happened, and any new error output.
   - Better prompt example: `That returned an empty array instead of the 3 rows I expected. Here's the log: …`
3. Provided constraints late in the thread
   - Impact: Earlier suggestions had to be revised once constraints surfaced.
   - Fix: List constraints (OS, versions, permissions) in your opening prompt.
   - Better prompt example: `I'm on Node 20, macOS, no root access. Goal: …`

## Miscommunication risks (3–5)
- Risk: Goal drift after a pivot
  Signal: The assistant asks "just to confirm, are we still working on X?"
  Mitigation: Re-state the goal explicitly whenever you change direction.

- Risk: Ambiguous failure reports
  Signal: The assistant asks "what exactly happened?"
  Mitigation: Include expected vs. actual output and any new errors.

- Risk: Implicit constraints
  Signal: The assistant suggests something your environment can't support.
  Mitigation: Front-load environment details in the first message.

## The best next prompt (copy/paste)
Use this next time:

```text
Goal:
<one sentence>

Current state:
<what is true right now>

Constraints:
<hardware/time/format/safety constraints>

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
- "here's the full stack trace from the deploy"
- "actually let's switch to fixing the auth bug instead"
- "that didn't work"

## Unknowns / missing context
- The first few turns were not included — earlier context may change scoring.
- It's unclear whether the goal pivot was planned or reactive.

</details>

## License

[MIT](LICENSE)
