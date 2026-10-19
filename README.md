# Launchcraft — Governance GTM Builder

A personal product marketing project prepared for John Miranda, inspired by his experience in enterprise AI governance and go-to-market planning. The sample brief describes a fictional governance platform. Choose a buyer, industry, objective, capabilities, date, launch window, and resource level; build six editable deliverables, review claim patterns, and export your work.

## Run locally

Open index.html directly, or run:

```sh
python3 -m http.server 8877 --bind 127.0.0.1
```

Visit http://localhost:8877. Stop the server with Ctrl+C.

## What works

- Generates positioning, a dated launch schedule, sales brief, three-message email sequence, 15-minute demo script, and measurement plan.
- Changes content based on selected buyer, industry, goal, capabilities, resources, and timeline.
- Lets you edit every deliverable and switch between them without losing edits.
- Flags quantitative, absolute, regulatory, analyst, and customer-reference patterns for review.
- Downloads the edited package as Markdown, schedule rows as CSV, and the full workspace as JSON.
- Reopens valid JSON projects using Open project; asks before replacing existing work.
- Optional browser storage preserves the workspace after reload. Reset clears the saved copy.

CSV export reads the edited schedule's dated task blocks. Preserve the Date / Task / Proposed owner / Readiness gate structure for CSV. Markdown and JSON preserve arbitrary text edits. Owner fields are proposed functions, not real assignments. Checks are heuristic flags, not factual verification.

## Generation method

This is a dependency-free, template-driven application. No model/API is connected. Additional freeform context is appended as an unverified planning input; it is not semantically interpreted. An AI backend can be added later, but this project does not pretend to call one.

## Privacy and evidence

All processing runs in the browser. There are no external network requests, analytics, credentials, lead lists, or original employer documents. Browser saving is opt-in. Sample capabilities are illustrative; verify real product availability and claims before using outputs externally. Generated drafts are new portfolio work, not proof of John's historical ownership or results. See docs/SOURCES.md and docs/JOHN_REVIEW.md.

## Files

- index.html: brief inputs and editing interface
- styles.css: responsive styling
- app.js: generation, edits, review, import/export, and optional storage
- tests/core.test.cjs: generation and validation checks
- docs/: provenance and John review checklist

## Tests

```sh
node --check app.js
node tests/core.test.cjs
```

Core checks cover 162 combinations of buyer, industry, objective, timeline, and resource settings, plus validation, selected capabilities, and dates. Browser checks exercised generation, objective-specific metrics, editing, claim flags, and a JSON download. Browser import and storage round-trip are not yet verified.

## Git and publishing

The local folder is initialized as a Git repository on main, with no remote, commits, or pushes. John can make the first commit:

```sh
git add .
git commit -m "Add Launchcraft governance GTM builder"
```

The ZIP excludes .git metadata. After extracting, run git init -b main if needed. John can create and connect his own remote later. Publish index.html, styles.css, and app.js to a static host; no build command or server backend is required. Localhost is a local preview, not a public deployment.

## Guided workflow

The interface now guides users through four stages: Define → Shape the story → Plan execution → Review & export. Use Continue and Back, or the progress navigation, to move through the package. Edits stay intact when navigating between stages. Final review includes claim checks, draft summaries, and exports. Rebuilding from an edited brief still asks before replacing drafts.