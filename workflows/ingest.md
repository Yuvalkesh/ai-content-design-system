# Workflow: Ingest

## Trigger
- A new post ships (post-final.md created in pipeline output)
- A new source dropped into `sources/` (transcript, article)
- Yuval says "ingest this"

## Inputs needed
- Path to the source file
- Channel (fb-hebrew | li-english | landing-page | price-quote | transcript | article)
- Performance data if available (reach, reactions, comments, shares, conversions)

## Procedure

1. **Read the source file fully.** Don't skim.

2. **Discuss takeaways with Yuval** in 3 lines:
   - One-line summary of what this is
   - Suggested patterns/hooks/themes (link to existing wiki entities by name)
   - One-line proposed slug

3. **Wait for Yuval's confirmation or correction.** Don't proceed until OK.

4. **Create the asset entity page** at `wiki/assets/<channel>/<YYYY-MM-DD>-<slug>.md` using `templates/asset.md`. Fill all frontmatter fields. Use real data, no nulls except where genuinely missing.

5. **For each pattern/hook/theme tagged on the asset, update its entity page:**
   - Increment `evidence_count`
   - Recompute `avg_perf` (mean of all assets using it)
   - Update `top_examples` if this asset's perf is in the top 3 for that pattern/channel
   - Add backlink

6. **Append to `log.md`:**

   ```
   ## [YYYY-MM-DD HH:MM] ingest | <title>
   - channel: <x>
   - patterns: [<list>]
   - hooks: [<list>]
   - themes: [<list>]
   - perf: <one-line summary>
   - asset: wiki/assets/<channel>/<file>.md
   ```

7. **Update `index.md`** by regenerating it from a scan of all `wiki/**/*.md` files (one line per file, grouped by entity type).

8. **Git commit:**

   ```bash
   git add -A
   git commit -m "ingest: <title>"
   ```

## Failure modes
- If the source has no perf data yet, set `status: shipped-pending-perf` and revisit on next ingest.
- If patterns/hooks proposed don't exist as entity pages, ask Yuval before creating new ones.
- If perf shows the asset failed badly, still ingest — failures teach more than wins.

## Commit message convention
- New post: `ingest: <slug>`
- New source: `ingest: source <slug>`
- New transcript: `ingest: transcript <slug>`
