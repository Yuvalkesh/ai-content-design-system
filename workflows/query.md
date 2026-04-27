# Workflow: Query

## Trigger
Yuval asks the wiki a question. Examples:
- "What hooks should I use for an LI post about agent business?"
- "Which patterns work best for ICP=Hebrew non-tech founders?"
- "What did we decide about LP free-tier strategy?"

## Procedure

1. **Start at `index.md`.** Identify candidate entity pages by tag/name match.

2. **Read full entity pages.** Never read partial chunks. The wiki is small enough to read whole pages.

3. **Follow backlinks** — for each candidate page, follow its `[[links]]` one hop to find related entities.

4. **Synthesize answer with inline citations.** Format:
   - Each claim cites the wiki page it came from (e.g., "(per `wiki/patterns/binary-closer.md`)")
   - Quantitative claims cite the source asset (e.g., "8.4K avg reach across 23 posts — see `wiki/patterns/binary-closer.md`")

5. **Ask Yuval: "File this answer back as a wiki page?"**
   - If yes and the answer is a decision → save to `wiki/decisions/YYYY-MM-DD-<topic>.md` using `templates/decision.md`
   - If yes and the answer is a synthesis → save to appropriate folder (theme, pattern, story)
   - If no, just answer in chat

6. **Append to `log.md`:**

   ```
   ## [YYYY-MM-DD HH:MM] query | <question summary>
   - pages read: [<list>]
   - filed back: <path or "no">
   ```

7. **If filed back, git commit:**

   ```bash
   git add -A
   git commit -m "query: <topic> filed to <path>"
   ```

## Failure modes
- If no relevant pages found, say so explicitly. Don't fabricate.
- If pages contradict, surface the contradiction — don't pick a side silently. Flag for `lint`.
