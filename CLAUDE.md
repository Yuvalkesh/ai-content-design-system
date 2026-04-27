# CLAUDE.md — AI Content Design System

This is an **AI Content Design System** — an LLM-maintained knowledge base in the Karpathy LLM Wiki pattern. If you're an AI agent reading this file, read it fully before doing anything else.

## What this is

A folder of markdown files an AI agent actively maintains as a compounding knowledge base for one person's (or one brand's) content creation. Replaces RAG over raw documents with pre-compiled, interlinked entity pages.

This repo is a **template**. The owner of the repo populates it with their own voices, patterns, and shipped posts over time. Each ingest makes the next post smarter.

## Three layers

| Layer | Owner | Mutability |
|---|---|---|
| `sources/` | Human curates | Immutable — read, never write |
| `wiki/` | LLM owns | Create, update, cross-reference |
| Schema (this file) | Human writes | Stable contract |

## Entity types (frontmatter contracts)

Every wiki page has YAML frontmatter. See `templates/` for examples.

- **asset** — one shipped post / LP / quote (see `templates/asset.md`)
- **pattern** | **hook** | **theme** — recurring craft elements (see `templates/pattern.md`)
- **voice** — channel voice profile (see `templates/voice.md`)
- **agent** — board member (see `templates/agent.md`)
- **decision** — board output filed back as wiki page (see `templates/decision.md`)
- **lesson** — feedback rule (see `templates/lesson.md`)

## Workflows

Five operating procedures live in `workflows/`:

- `workflows/ingest.md` — add a new post / source / asset
- `workflows/query.md` — answer a question against the wiki
- `workflows/consult-board.md` — bring in CMO / COO / Ken / Maya — files decision back
- `workflows/lint.md` — health check (orphans, contradictions, stale, broken refs)
- `workflows/compile-asset.md` — generate writer-identity / channel rules / LP brief from current wiki state

## Tidiness rules (non-negotiable)

1. **One entity = one file.** No mega-files.
2. **Frontmatter mandatory** — `type`, plus type-specific fields per template.
3. **Slugs are kebab-case.** Hebrew posts use transliterated slugs.
4. **Backlinks mandatory** — every claim cites a `sources/` or `wiki/` page using `[[link]]` or path.
5. **`index.md` is auto-regenerated** on every ingest. Never hand-edit.
6. **`log.md` is append-only.** Never edit history.
7. **Weekly lint** — Sundays. Read `workflows/lint.md`.
8. **Git: every ingest = one commit, every lint = one commit, every decision = one commit.**

## Phase 1 scope (recommended first steps)

This repo is for **content designers / UX writers** building a content brain for one product. Keep scope tight:

- Pick **one product surface** to start with: errors, empty states, onboarding, or transactional copy. Just one.
- Add **one voice** in `wiki/voices/` describing how your product speaks on that surface.
- Drop **5 real strings** from production into `sources/<surface>/` — one file per string, with 1-2 lines of context above each.
- Run `/wiki-ingest` to populate `wiki/assets/`, `patterns/`, `hooks/`, `themes/`.
- Run `/wiki-query` to ask the system what tone you use, what patterns recur.
- Run `/wiki-compile draft "<description of next screen>"` to generate a voice-correct draft with citations.

Expand to a second surface only after Phase 1 is producing usable drafts.

## Out of scope (Phase 2+)

Marketing copy, blog posts, email sequences. This repo is for **product copy** (microcopy, errors, empty states, onboarding, transactional). If you want a marketing-content wiki, run a second instance of this template — don't mix scopes in one repo.

## Conventions

- **File naming:** `YYYY-MM-DD-<slug>.md` for assets and decisions; `<name>.md` for patterns/hooks/themes/voices/agents/lessons.
- **Backlinks:** Use Obsidian-style `[[entity-name]]` for entity-to-entity. Use relative paths for sources.
- **Dates:** Always YYYY-MM-DD.
- **Frontmatter source field:** points to the immutable source the entity was derived from.

## When in doubt

Ask the repo owner. Don't invent rules. Don't expand scope.
