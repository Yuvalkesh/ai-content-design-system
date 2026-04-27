# AI Content Design System

A markdown-based content brain for one writer or one brand. Built on the [Karpathy LLM Wiki pattern](https://karpathy.bearblog.dev/llm-wiki/) — knowledge as compounding markdown files, not RAG over PDFs.

The bet: every post you ship makes the next post smarter, because every post becomes one entity page in `wiki/` with backlinks to its patterns, hooks, themes, and voice.

---

## Quick start

1. Click **Use this template** at the top of this GitHub repo. Pick a name and visibility for your copy.
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
   /wiki-compile brief
   ```

That's it. The five `/wiki-*` slash commands are bundled with this repo (in `.claude/skills/`) — they work the moment you open the repo in Claude Code.

---

## What's in here

```
templates/        Frontmatter contracts (asset, voice, pattern, lesson, agent, decision)
workflows/        Operating procedures (ingest, query, lint, consult-board, compile)
wiki/             Your knowledge base — populated as you ingest content
sources/          Drop your raw shipped posts here. Immutable archive.
CLAUDE.md         Schema rules for the AI maintaining this repo. Read first.
principles.md     Voice philosophy.
index.md          Auto-regenerated catalog of everything in wiki/.
log.md            Append-only history of changes.
```

---

## How it works

1. You drop your top 5 shipped posts into `sources/<channel>/posts/`.
2. `/wiki-ingest` reads each one, creates an entity page in `wiki/assets/`, and updates the `patterns/`, `hooks/`, `themes/` your post used.
3. `/wiki-query` answers questions against the wiki — "what makes my best posts work?", "show me my voice rules" — by following backlinks.
4. `/wiki-compile brief <topic>` generates an evidence-backed brief for your next post.
5. After you ship the new post, drop it in `sources/`, run `/wiki-ingest` again. The cycle compounds.

---

## Why this beats RAG

- **No vector DB.** Just markdown files in git.
- **No embedding cost.** No re-indexing.
- **Human-readable.** Open the folder in Obsidian — same wiki, with graph view.
- **Versioned.** Every change is a commit. Roll back, branch, diff.
- **Portable.** Fork the repo, clone it, anyone with Claude Code can use it.

---

## Next steps

Read `CLAUDE.md` to understand the schema. Read `workflows/` to see how each command operates. Then start with one channel, five posts, and one `/wiki-ingest`.
