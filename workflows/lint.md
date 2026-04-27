# Workflow: Lint

## Trigger
- Weekly (Sundays 6pm — schedule TBD)
- On-demand via `/wiki-lint`
- Before any major Phase milestone

## Checks

### 1. Orphans
A wiki page has no inbound links from any other wiki page.

**Action:** List orphans. For each, ask Yuval: keep, delete, or merge?

### 2. Contradictions
Two pages making opposing claims (especially in `lessons/` and `voices/`).

**Action:** Surface the pair with quoted lines. Ask Yuval to resolve.

### 3. Stale claims
- Asset perf: `last_lint` more than 30 days ago AND `status: shipped` (perf may have changed)
- Pattern `avg_perf`: more than 14 days since last recompute

**Action:** Recompute perf where possible from `sources/` data. Flag what can't be recomputed.

### 4. Broken backlinks
A `[[link]]` or relative path points to a deleted/renamed page.

**Action:** List broken links + suggest replacements. Yuval approves fix.

### 5. Missing pages
A concept appears in 3+ pages but has no entity page of its own.

**Action:** List candidate concepts + counts. Yuval picks which to promote to entities.

### 6. Coverage gaps
- Asset pages with empty `patterns: []`
- Patterns with `evidence_count: 0`
- Agents with no `last_decision`

**Action:** List gaps. Some are OK (new patterns awaiting evidence), some are bugs.

## Procedure

1. **Run all 6 checks.** Build a structured report.

2. **Save report** to `wiki/lint-reports/YYYY-MM-DD.md` (create folder on first run).

3. **Append to `log.md`:**

   ```
   ## [YYYY-MM-DD HH:MM] lint
   - orphans: <count>
   - contradictions: <count>
   - stale: <count>
   - broken_links: <count>
   - missing_pages: <count>
   - coverage_gaps: <count>
   - report: wiki/lint-reports/<file>.md
   ```

4. **Surface the report to Yuval.** He triages. Lint never auto-fixes — it always asks.

5. **Git commit:**

   ```bash
   git add -A
   git commit -m "lint: <YYYY-MM-DD>"
   ```

## Health metric
Lint is healthy if:
- orphans ≤ 3
- contradictions = 0
- stale ≤ 5
- broken_links = 0
- coverage_gaps trending down week-over-week
