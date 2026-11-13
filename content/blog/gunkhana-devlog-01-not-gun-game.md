---
title: "Gunkhana Devlog 01: \"Basically Gun Game\" (It Was Not Gun Game)"
date: 2026-09-11
tags: ["gunkhana", "devlog"]
description: "A 2v2 arena shooter starts with a one-line pitch, a misunderstanding, and 70 tasks."
---

The pitch I typed was one line: a really simple 2v2 small-arena FPS, "basically gun game from Modern Warfare."

I did not mean Gun Game. I meant **Gunfight**: two against two, everyone gets the same random loadout each round, no respawns, first to six. The build agent (Claude, running in a loop I call the Game Forge) asked which one I meant before writing a line. Good thing, or this would be a very different blog.

Then I made it less simple. The thing that would set it apart is the movement, so the pitch became: Mirror's Edge parkour, Tarkov gunplay, Gunfight rules. The plan grew from "really simple" to 38 tasks, then 40, then 47, then 70.

![The training map: coloured boxes on a grey floor](/blog/gunkhana/training.jpg)

*What the whole game looked like at first. This box garden survives as the training map.*

## How the forge works

Every task is one sentence with a test attached. The agent builds it, runs the tests, commits, and takes the next one. Collision is hand-written box math instead of the engine's physics, so the whole game can be played headless by tests. Nobody has to watch.

The first 14 tasks (arena plus movement) passed first try with 77 tests. Guns and fall damage went in next: 117 tests. By the end of the first long push all 70 tasks were done and 433 tests passed: rounds, spawns, random loadouts, spectating, bots that move, fight and throw grenades, an overtime flag, a match to six.

## Then I played it

My first playtest note: the movement "didn't feel that great." I couldn't tell when I was wall-running, and I didn't know which button was slide.

433 green tests, and the player can't find the slide button. That is the gap this whole devlog series lives in. Tests can tell you the wall-run lasts 1.2 seconds. They cannot tell you it feels like nothing.

The fix was camera work: the view rolls ten degrees toward the wall, the field of view opens up with speed, landings dip the camera. Same wall-run, now you can feel it.

Decisions I made that day that still stand:

- Bots throw grenades.
- Fall damage starts at three times your own height.
- Some buildings have to be too tall to climb. (The agent checked: you could reach the top of the backdrop from a van roof. It raised them to 14 metres and wrote a test called `test_backdrops_too_tall_to_climb`.)

Next week: I spend an entire day arguing with a robot about how to climb onto a box.
