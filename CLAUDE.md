# CLAUDE.md

Guidance for Claude Code (and anyone else) working in this repository.

## What this is

A static website (plain HTML pages + `support.js`, no build step, no bundler,
no framework, no tests, no CI) deployed to Cloudflare via `wrangler.jsonc`.
Because there is nothing between "a file changes" and "it's live," treat
every change to `main` as a production deploy.

## Workflow rules

- **Never commit directly to `main`.** Every change goes on a feature branch
  (e.g. `git checkout -b fix/contact-form-typo`), gets pushed, and is opened
  as a pull request for review before merging.
- **Never force-push, `git reset --hard`, or otherwise rewrite history** on
  `main` or any shared branch.
- **Always show the diff and get explicit confirmation before committing or
  pushing.** Don't assume approval carries over from a previous change.
- Only commit when explicitly asked to.
