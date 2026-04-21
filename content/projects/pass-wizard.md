---
title: "Pass Wizard"
description: "A fork-and-fill study-site framework. Bring your own source material, let an LLM do the rest."
weight: 6
icon: "&#128302;"
status: "active"
tech: ["HTML", "CSS", "JavaScript", "Python", "Claude API", "ollama"]
github: "https://github.com/AnarchySC/pass-wizard"
cta_url: "https://github.com/AnarchySC/pass-wizard"
cta_label: "Fork on GitHub"
---

## What it is

Pass Wizard is a **study-site framework** for certification exams. It ships the UI &mdash; course reader, practice quiz, skill tree, story-driven companion, and a local progress dashboard &mdash; and gets out of your way. You fork the repo, drop your own source material into a local folder, and point a generator at it. An LLM reads the material and writes a full study site for whatever exam you're chasing.

No account. No backend. No tracking. Your progress lives in `localStorage`, your source material never leaves your machine, and the generated content stays local unless you choose to commit it.

## How it works

<div class="feature-grid">
  <div class="feature-card">
    <h4>1. Fork</h4>
    <p>Clone the repo. Pure static HTML/CSS/JS &mdash; no build step, no node_modules.</p>
  </div>
  <div class="feature-card">
    <h4>2. Scaffold an exam</h4>
    <p><code>tools/new-exam.py --code AZ-500</code> creates the folder structure and a minimal <code>meta.json</code>.</p>
  </div>
  <div class="feature-card">
    <h4>3. Drop your sources</h4>
    <p>PDFs, markdown, text dumps &mdash; anything readable goes into <code>dropbox/&lt;slug&gt;/</code>. Gitignored by default.</p>
  </div>
  <div class="feature-card">
    <h4>4. Generate</h4>
    <p><code>tools/generate.py &lt;slug&gt; all</code> hands the sources to an LLM, which writes the quiz bank, course modules, skill tree, and companion guides.</p>
  </div>
  <div class="feature-card">
    <h4>5. Study</h4>
    <p><code>python3 -m http.server</code> and open the site. Everything runs locally.</p>
  </div>
</div>

## What the framework ships

- **Exam-agnostic quiz engine** &mdash; weighted question bank, domain filtering, weak-question drilling, session history.
- **Course reader** &mdash; clean typography, mobile-first, works great on a phone.
- **Skill tree** &mdash; RPG-style progression map with tiered unlocks.
- **Companion** &mdash; interactive story-driven walkthroughs. Learn by playing, not memorizing.
- **Progress dashboard** &mdash; sparkline history, mastery grid, weakest questions. Export and import as JSON.

## LLM backends

One adapter interface, two backends out of the box:

- **Claude API** *(default)* &mdash; best generation quality. Set `ANTHROPIC_API_KEY` and go. Prompt caching keeps costs down on re-runs.
- **Ollama** *(local)* &mdash; no API key, no cloud. Point at any local Ollama server via `OLLAMA_HOST`. Slower, but free and offline.

Swap with `PW_LLM_BACKEND=claude|ollama`. Bringing a third backend is a single file.

## Privacy

- **No account, no backend.** Everything runs client-side.
- **No analytics, no tracking pixels, no third-party scripts.**
- **No Google Fonts.** Self-hosted or system fallback &mdash; no IP leak on page load.
- **Your progress lives in `localStorage`** under `passwizard:<exam-code>`. It never leaves your device.
- **Your source material stays local.** The `dropbox/` folder is gitignored. Generated content is gitignored. Nothing goes to the public repo unless you explicitly stage it.

## Tech

Vanilla HTML, CSS, and JavaScript for the site &mdash; no frameworks, no bundlers, no dependencies. Python for the generator tooling. Static output hosts anywhere: GitHub Pages, Netlify, a USB stick, `python3 -m http.server`.

## Status

The framework is under active development. The UI engine is stable (built on the AZ-104 content). The generator pipeline is being rolled out in phases &mdash; see [`docs/framework.md`](https://github.com/AnarchySC/pass-wizard/blob/main/docs/framework.md) in the repo for the current design and phase plan.

## License

MIT.
