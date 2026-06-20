---
name: update-github-info
description: Draft Mona site updates from GitHub Blog, GitHub Changelog, and Awesome Copilot workflows; open a PR for review.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
permissions:
  contents: read
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit: {}
  web-fetch: {}
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` for Mona's voice and site priorities.
Fetch `https://github.blog/latest/`, `https://github.blog/changelog/`, and `https://awesome-copilot.github.com/workflows/` with `web-fetch`.
Update `site/content/github-info.md` with a short, accurate summary of the latest GitHub Blog, GitHub Changelog, and Awesome Copilot workflows updates.
Open a pull request for Mona to review using `safe-outputs.create-pull-request`.
Use a pull request title that mentions Mona, GitHub Info, or a website update.
Ensure the generated pull request includes changes to `site/content/github-info.md`.
