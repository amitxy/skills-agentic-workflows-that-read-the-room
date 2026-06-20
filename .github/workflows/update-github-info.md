---
name: update-github-info
description: Draft Mona site updates from GitHub Blog and Changelog and open a PR for review.
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
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` for Mona's voice and site priorities.
Fetch `https://github.blog/latest/` and `https://github.blog/changelog/` with `web-fetch`.
Update `site/content/github-info.md` with a short, accurate summary of the latest GitHub Blog and GitHub Changelog updates.
Open a pull request for Mona to review using `safe-outputs.create-pull-request`.
