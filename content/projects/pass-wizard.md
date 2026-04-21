---
title: "Pass Wizard"
description: "Single-pane certification study platform. Courses, practice quizzes, and skill trees for every exam you're chasing."
weight: 6
icon: "&#128302;"
status: "active"
tech: ["HTML", "CSS", "JavaScript", "localStorage"]
github: "https://github.com/AnarchySC/pass-wizard"
cta_url: "https://anarchygames.org/pass-wizard/"
cta_label: "Launch App"
---

## What it is

One URL, one UI, one progress store &mdash; for every cert you're chasing. Pick an exam from the landing page and you get a full study environment: course modules, a practice quiz, a skill tree, a story-driven companion, and your own progress dashboard. No account. No backend. Works offline after the first load.

## Supported exams

| Code | Name | Course | Quiz | Skill Tree | Companion |
|------|------|:------:|:----:|:----------:|:---------:|
| AZ-104 | Azure Administrator | &#9989; | &#9989; | &#128679; | &#128679; |
| AZ-400 | DevOps Engineer | &#128679; | &#9989; | &mdash; | &mdash; |
| AZ-305 | Solutions Architect | &#128679; | &#9989; | &mdash; | &mdash; |
| PSM-I | Scrum Master | &#128679; | &#9989; | &mdash; | &mdash; |

More exams land as the content is written. The quiz engine is exam-agnostic, so adding a new exam is a matter of dropping in a question bank and a `meta.json`.

## What's inside each exam

<div class="feature-grid">
  <div class="feature-card">
    <h4>Course</h4>
    <p>Walk-through modules with explanations, examples, and hands-on labs. Read on your desk or your phone.</p>
  </div>
  <div class="feature-card">
    <h4>Practice Quiz</h4>
    <p>Weighted question bank with domain filtering, weak-question drilling, and session history.</p>
  </div>
  <div class="feature-card">
    <h4>Skill Tree</h4>
    <p>RPG-style progression map. See what you've mastered and where the gaps are.</p>
  </div>
  <div class="feature-card">
    <h4>Companion</h4>
    <p>Interactive story-driven walkthroughs. Learn by playing, not memorizing.</p>
  </div>
  <div class="feature-card">
    <h4>Progress</h4>
    <p>Sparkline history, mastery grid, and your weakest questions &mdash; all tracked locally.</p>
  </div>
</div>

## Privacy

- **No account, no backend.** Everything runs client-side.
- **No analytics, no tracking pixels, no third-party scripts.**
- **No Google Fonts.** Self-hosted or system fallback &mdash; no IP leak on page load.
- **Your progress lives in `localStorage`** under `passwizard:<exam-code>`. It never leaves your device.
- **Export/import** your progress as JSON from the Progress tab to back it up or move between devices.

## Tech

Vanilla HTML, CSS, and JavaScript. No frameworks. No build step. No dependencies. Static site, hosts anywhere. Clone the repo, run `python3 -m http.server`, and you're up.

## License

MIT.
