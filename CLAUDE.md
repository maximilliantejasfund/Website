# CLAUDE.md

Guidance for Claude Code (and anyone else) working in this repository.

## What this is

A static website (plain HTML pages + `support.js`, no build step, no bundler,
no framework, no tests, no CI) deployed to Cloudflare via `wrangler.jsonc`.
Because there is nothing between "a file changes" and "it's live," treat
every change to `main` as a production deploy.

## Workflow rules

- **Commit directly to `main`** — no feature branches or PRs required for
  routine changes.
- **Before every push to `main`, tag the current HEAD first**, e.g.
  `git tag pre-YYYY-MM-DD-N <current main HEAD>` and push the tag
  (`git push origin <tag>`) *before* pushing the new commit(s). This makes any
  bad push a one-command rollback: `git reset --hard <tag>` (or
  `git revert`) instead of digging through history under pressure.
- **Always show the full diff and get explicit "yes, push" confirmation
  before pushing to `main`.** Don't assume approval carries over from a
  previous change.
- **Never force-push, `git reset --hard`, or otherwise rewrite history on a
  pushed commit** — only ever move forward (new commits, or a `git revert`)
  once something is on `origin/main`.
- Only commit when explicitly asked to.
