# Workflow: Compile Asset

## Trigger
- Yuval is about to draft a new post / LP / quote
- Yuval wants a refreshed writer-identity / channel rules document
- `/wiki-compile <channel>` slash command

## What this does
Generates a fresh, evidence-backed artifact (writer-identity, channel rules, LP brief) from the CURRENT wiki state. The artifact is a *generated output*, not a hand-edited file. It replaces the manual upkeep of writer-identity files in `C-core/`.

## Inputs
- Channel: `fb-hebrew` | `li-english` | `landing-page` | `price-quote`
- Output type: `writer-identity` | `channel-rules` | `brief`

## Procedure

1. **Load the relevant voice page:** `wiki/voices/yuval-<channel>.md`

2. **Load the channel page:** `wiki/channels/<channel>.md`

3. **Load all patterns/hooks/themes** that have `applies_to` containing this channel.

4. **Load all lessons** with `applies_to` containing this channel.

5. **Load top 10 asset pages** by perf for this channel (sorted by primary perf metric — reach for fb-hebrew, impressions for li-english, conversions for LPs/quotes).

6. **Synthesize the artifact.** Structure depends on output type:

   - **writer-identity**: voice + 14-style rules + kill list + signature moves + top examples
   - **channel-rules**: format constraints + posting cadence + audience notes + perf benchmarks
   - **brief**: one-shot brief for the next post — recommended pattern + hook + theme + ICP tag + opening line options

7. **Save to** `wiki/compiled/<channel>-<output-type>-<YYYY-MM-DD>.md` (create folder on first run).

8. **Append to `log.md`:**

   ```
   ## [YYYY-MM-DD HH:MM] compile | <channel> | <output-type>
   - file: wiki/compiled/<file>.md
   ```

9. **Git commit:**

   ```bash
   git add -A
   git commit -m "compile: <channel> <output-type>"
   ```

## Important
- Compiled artifacts are never edited by hand. To change them, change the source entities and recompile.
- Compiled artifacts have a `last_compiled` field in frontmatter so consumers know how fresh they are.
- If a pipeline (e.g., `/pipeline-facebook-hebrew`) wants to use the latest writer-identity, it reads the latest compiled file.
