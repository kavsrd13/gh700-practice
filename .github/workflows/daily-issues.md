---
name: "Daily Issues Report"
description: "Summarises open issues and flags stale ones"
on:
  schedule: daily on weekdays
  workflow_dispatch:
permissions:
  contents: read
  issues: read
engine: copilot
tools:
  github:
safe-outputs:
  create-issue:
    title-prefix: "[daily-report] "
    labels: [report]
    max: 1
---

# Daily Issues Report

Create a summary of the open issues in this repository.

## What to include

- New issues opened in the last 24 hours
- Issues open for more than 14 days (flag these as stale)
- Any issue that looks blocked or high risk

## Rules

- Do not close, edit, or delete any issue.
- Do not invent issues. Only report what exists.
- Keep the report under 200 words, in bullet points.

## Self-check

Before finishing, review your draft against the list above. Remove anything not supported by the data, then publish the final report as one issue.