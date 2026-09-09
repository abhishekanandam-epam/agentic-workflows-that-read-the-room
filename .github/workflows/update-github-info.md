---
name: update-github-info
description: Draft updates for Mona's GitHub Info site using official GitHub sources and open a pull request for review.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
tools:
  edit:
  web-fetch:
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
network:
  allowed:
    - github.blog
    - github.com
---

# Update Mona's GitHub Info site

Read `notes/mona-notes.md` before making any changes.

Use public guidance from the GitHub Blog and GitHub Changelog as the primary sources for current product information and release notes.

- Read `notes/mona-notes.md`
- Use web-fetch to read https://github.blog/latest/
- Use web-fetch to read https://github.blog/changelog/
- If you need repository guidance or reference files, use GitHub repository API tools instead of terminal, CLI, or sandboxed commands.

Update `site/content/github-info.md` with concise, practical content that reflects the latest GitHub Blog and GitHub Changelog updates while staying consistent with Mona's notes and the site's purpose.

When you summarize or draft changes, include helpful context and source references from the GitHub Blog and GitHub Changelog so Mona can review the updates quickly.

Open a pull request for Mona to review using `safe-outputs` with `create-pull-request`. Do not write directly to `main`.

Your work should prepare a proposed update for the site and use a pull request so Mona can approve or revise it before merge.
