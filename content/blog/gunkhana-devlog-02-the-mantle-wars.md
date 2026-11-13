---
title: "Gunkhana Devlog 02: The Mantle Wars"
date: 2026-09-18
tags: ["gunkhana", "devlog", "movement"]
description: "Fourteen playtests about one question: how should a person get on top of a box?"
---

Parkour is the point of Gunkhana, so the parkour has to be right. Here is the complete history of one verb, "mantle", told through my playtest notes.

**Playtest 2.** "If the height is right, it should mantle the ledge." Reasonable. Built.

**Playtest 4.** Thin 40 cm walls made me mantle sideways onto nothing. New rule: the top needs standing room.

**Playtest 9.** "Jumping to mantle raises me up in the air." The agent reproduced it without a screen: a running jump at a one-metre crate started a wall-climb instead and launched my feet to about 3.2 metres. I had built a crate-powered trampoline.

**Playtest 10.** "Mantling should not be automatic. User must push jump to mantle."

**Playtest 11.** "He still steps up onto smaller boxes automatically."

**Playtest 12.** Now it was "too sensitive", and I kept mantling *over* big boxes I wanted to stand on. Final rule: tap jump to climb onto it, hold jump to kong over it.

**Playtest 13.** Couldn't grab ledges out of a wall-run. I suggested jump-then-grab instead. The robot agreed, which I choose to believe was sincere.

**Playtest 14.** Running into low boxes froze me in a climb pose. New rule: wall-runs and wall-climbs only work on things at least three metres tall. Small boxes are for vaulting.

![The first Kabukicho map at night](/blog/gunkhana/kabukicho-old.jpg)

*Kabukicho, the first real map. Every one of those boxes got mantled wrong at least once.*

## Then it was slippery

Around playtest 5 I asked for weight and momentum: your body plus your guns, Tarkov style, so a machine gunner turns like a truck. The agent built it faithfully. By playtest 17 my note was that movement felt "slidy and slippery" and "for FPS it should be responsive."

So ground acceleration went from 24 to 60, braking from 20 to 60, and the weight penalty dropped by more than half. Momentum stayed in the places where it is fun: sprint ramp, slides, wall moves.

## What I learned

1. Every automatic movement rule is one playtest away from being a bug report.
2. "Make it realistic" and "make it responsive" are enemies. Pick responsive on the ground and realistic in the air.
3. A physics sim that runs without a screen is worth it. Every one of these complaints became a regression test, so playtest 9's trampoline can never come back.

Other things added mid-argument, because I kept thinking of them: lean on Q and E, a flashlight on F, grenades you charge by holding G, a sprint that lasts seven seconds and refills in four.

Next week: the game gets sound, and I get a pinball machine.
