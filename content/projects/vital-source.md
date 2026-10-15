---
title: "Project Vital Source"
description: "Learn Linux in the terminal. Drill each core skill until it's automatic, then drill them together."
weight: 2
icon: "&#128187;"
status: "active"
tech: ["Bash", "Python", "Docker", "Debian"]
github: "https://github.com/AnarchySC/vital-source"
cta_url: "https://github.com/AnarchySC/vital-source"
cta_label: "Get it on GitHub"
---

## The problem

The hard part of learning Linux isn't any single command. It's not knowing where to start, and not remembering what you learned last week. You won't remember a command you don't care about, and you won't care about one until you know what it gets you out of.

Vital Source starts every lesson with a situation you've been in: the disk is full, a download won't open, you know the file is here somewhere. The command comes second, as the way out.

## How it works

<div class="feature-grid">
  <div class="feature-card">
    <h4>1. One skill at a time</h4>
    <p>The ten things you actually do in a terminal, plus lesson zero: how to look anything up.</p>
  </div>
  <div class="feature-card">
    <h4>2. Reps, not reading</h4>
    <p>Every rep builds a fresh scenario with new files, names and folders. You memorize the skill, not the answer.</p>
  </div>
  <div class="feature-card">
    <h4>3. Graded on results</h4>
    <p><code>drill check</code> looks at what you did, not what you typed. Any correct way passes.</p>
  </div>
  <div class="feature-card">
    <h4>4. Burned in</h4>
    <p>Five clean reps in a row, under the time target, with no hints. Right but slow means it isn't burned in yet.</p>
  </div>
  <div class="feature-card">
    <h4>5. Then combinations</h4>
    <p>Once each skill is automatic, you chain them together until the chains are automatic too.</p>
  </div>
</div>

## The skills

0. **Help yourself:** `tldr`, `--help | grep`, searching a `man` page instead of reading it, `man -k`
1. **Navigate:** `pwd`, `cd`, `ls -la`, absolute and relative paths
2. **Move things around:** `mkdir`, `cp`, `mv`, `rm`, wildcards
3. **Read files:** `cat`, `less`, `head`, `tail -f`
4. **Find things:** `find`, `grep -r`
5. **Inspect:** `du`, `df`, `stat`, `file`, `wc`
6. **Permissions:** `ls -l`, `chmod`, `chown`, `sudo`
7. **Pipes and redirection:** `|`, `>`, `sort`, `uniq`, `cut`
8. **Install software:** `curl`, `sha256sum`, `tar`, `apt`, from a real package repo of AnarchyGames titles
9. **Processes:** `ps`, `top`, `kill`, jobs
10. **Edit a config file:** `nano`, and enough vim to get out of it

## A sandbox you can't break

Everything runs in a disposable Debian container. `rm -rf` the whole thing if you want; `learn-linux --reset` hands you a fresh one in a second, and your progress stays put.

```
git clone https://github.com/AnarchySC/vital-source
cd vital-source
bin/learn-linux
drill start 0
```

You need Docker.

## Status

Lessons 0 to 2 are playable now. Lessons 3 to 10, the combination missions and the AnarchyGames package repo are next.
