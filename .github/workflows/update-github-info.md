---
name: update-github-info
description: Refresh site/content/github-info.md from the latest GitHub Blog and Changelog posts and open a pull request for Mona.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
engine:
  id: copilot
  copilot-sdk: true
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[github-info] "
    draft: true
---

# Update GitHub Info

Keep Mona's website content fresh with recent GitHub news.

## Instructions

1. Read `notes/mona-notes.md` and follow its editorial guidance.
2. Use web fetch to read `https://github.blog/latest/`.
3. Use web fetch to read `https://github.blog/changelog/`.
4. Update `site/content/github-info.md` with a short, practical summary of the most relevant recent stories, naming the source (GitHub Blog or GitHub Changelog) for each item and linking to it.
5. Preserve the existing structure and tone of the file; only change what the new stories justify.
6. Open a pull request with your changes so Mona can review them. Never write directly to `main`.

If there is nothing new worth adding, make no changes and do not open a pull request.
