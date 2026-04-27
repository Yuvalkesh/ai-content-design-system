# AI Content Design System

A markdown-based content brain for the product you write for. Built on the [Karpathy LLM Wiki pattern](https://karpathy.bearblog.dev/llm-wiki/) — knowledge as compounding markdown files, not RAG over PDFs.

The bet: every error message, empty state, or onboarding line you ship makes the next one easier to draft, because every shipped string becomes one entity in `wiki/` with backlinks to its patterns, hooks, themes, and product voice.

---

## Quick start

1. Click **Use this template** at the top of this GitHub repo. Pick a name (e.g. `acme-copy-brain`) and visibility for your copy.
2. Clone your new repo and `cd` into it:
   ```bash
   gh repo clone YOUR-USERNAME/your-repo-name
   cd your-repo-name
   ```
3. Open Claude Code:
   ```bash
   claude
   ```
4. Try your first three commands:
   ```
   /wiki-query "what does this template contain?"
   /wiki-ingest
   /wiki-compile draft "checkout failed — payment declined"
   ```

The five `/wiki-*` slash commands are bundled with this repo (in `.claude/skills/`) — they work the moment you open the repo in Claude Code.

---

## What's in here

```
templates/        Frontmatter contracts (asset, voice, pattern, lesson, agent, decision)
workflows/        Operating procedures (ingest, query, lint, consult-board, compile)
wiki/             Your product's content brain — populated as you ingest strings
sources/          Drop your shipped strings here. Immutable archive.
CLAUDE.md         Schema rules for the AI maintaining this repo. Read first.
principles.md     Voice philosophy.
index.md          Auto-regenerated catalog of everything in wiki/.
log.md            Append-only history of changes.
```

---

## How it works

1. You drop 1 real string from your product into `sources/<surface>/` — an error, an empty state, an onboarding line, or a CTA. One file. The one that's been on your mind.
2. `/wiki-ingest` reads it, creates an entity page in `wiki/assets/`, and names the `patterns/`, `hooks/`, `themes/` it uses.
3. `/wiki-query` answers questions against the wiki — "what tone do we use in error messages?", "show me our voice rules" — with citations to actual shipped strings.
4. `/wiki-compile draft <description>` generates a voice-correct draft for the next screen, with options each backed by past strings that shipped.
5. After the new string ships, drop it in `sources/`, run `/wiki-ingest` again. The cycle compounds.

---

## What this is for

You're a content designer or UX writer working on a product. You want:
- Your AI to actually know how your product talks.
- The voice & tone doc nobody reads to be replaced by a system that reads itself.
- A way to onboard new copywriters in 30 minutes by handing them a repo URL.
- Every shipped string to make the next one faster to draft.

This is for that.

---

## Why this beats RAG

- **No vector DB.** Just markdown files in git.
- **No embedding cost.** No re-indexing.
- **Human-readable.** Open the folder in Obsidian — same wiki, with graph view of how your strings connect.
- **Versioned.** Every change is a commit. Roll back, branch, diff.
- **Portable.** Fork the repo, clone it, anyone with Claude Code can use it.

---

## Next steps

Read `CLAUDE.md` to understand the schema. Read `workflows/` to see how each command operates. Then start with one product surface (errors, or empty states), one real string, and one `/wiki-ingest`. The first ingest is the seed.
