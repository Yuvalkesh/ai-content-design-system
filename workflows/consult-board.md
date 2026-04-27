# Workflow: Consult Board

## Trigger
- "Bring in the board" / "call in the board"
- "What would CMO say?" / "Ken, weigh in" / "Michal's take?"
- `/consult-board` slash command
- Any business decision Yuval is unsure about

## Board members (all weigh in by default)

| Agent | Role | Entity page |
|---|---|---|
| Yuval | CEO (decides) | `wiki/agents/ceo-yuval.md` |
| CMO | Mr. Traction Master | `wiki/agents/cmo-traction-master.md` |
| COO | Michal | `wiki/agents/coo-michal.md` |
| Ken | McKinsey advisor | `wiki/agents/ken-advisor.md` |
| Maya | Learning Architect | `wiki/agents/maya-ld.md` |

**Per Yuval's decision 2026-04-27:** Maya weighs in on every board call, not only learning-adjacent topics.

## Procedure

1. **Restate the question** in one sentence. Confirm with Yuval before proceeding.

2. **Load all 5 agent entity pages** fully. Internalize each agent's voice and heuristics.

3. **Pull related entities:**
   - If question touches content → load relevant patterns/themes/voice pages
   - If question touches an asset → load its asset page + perf
   - If question touches pricing → load `wiki/voices/yuval-quote.md` + recent quotes
   - If question touches LPs → load `wiki/channels/landing-page.md` + recent LPs

4. **Pull prior decisions on this topic.** Search `wiki/decisions/` by tag/title. Never re-decide what's already settled — reference and extend.

5. **Each agent weighs in IN THEIR VOICE.** Format:

   ```
   ## CMO — Mr. Traction Master
   [his take in his voice, citing wiki entities]

   ## COO — Michal
   [her take in her voice, citing wiki entities]

   ## Ken
   [his take — McKinsey style, data-driven, citing perf evidence]

   ## Maya
   [her take — learning architect lens, citing learner journey]
   ```

6. **CEO (Yuval) makes the call** — synthesizes the board, decides, states rationale.

7. **File the decision** as `wiki/decisions/YYYY-MM-DD-<topic-slug>.md` using `templates/decision.md`. Required fields: question, participants (all 5), sources_consulted, status, decision, rationale, followups.

8. **Update each agent's `last_decision` field** + add `[[YYYY-MM-DD-topic]]` backlink to their `recent_decisions` section.

9. **Append to `log.md`:**

   ```
   ## [YYYY-MM-DD HH:MM] decision | <topic>
   - participants: [yuval, cmo, coo, ken, maya]
   - status: decided
   - decision: <one-line>
   - file: wiki/decisions/<file>.md
   ```

10. **Git commit:**

    ```bash
    git add -A
    git commit -m "decision: <topic>"
    ```

## When to abbreviate
- For pure content tactical questions, you may consult only CMO + relevant voice/patterns. Skip Ken/Michal/Maya.
- For pricing/operations, skip Maya unless learner-facing.
- **But never skip filing the decision.** Even abbreviated calls produce a decision page.

## Failure modes
- If two agents disagree fundamentally, surface it. CEO breaks the tie. The disagreement gets noted in the decision.
- If sources_consulted is empty, the wiki failed to surface relevant entities — flag for lint.
