---
title: "Gunkhana Devlog 04: The Bots Were Gods, Then They Got Stuck on a Roof"
date: 2026-10-02
tags: ["gunkhana", "devlog", "ai"]
description: "Teaching bots to parkour, miss, forget, and stop playing when nobody is watching."
---

A parkour shooter needs bots that can parkour. You can't hand-draw paths for wall-runs and kongs across 16 maps, so the bots learn each map by trying it.

When a map loads, the game drops a one-metre grid on every floor and rooftop, then replays real player inputs (run, jump, wall-run, mantle) through the real movement code between nearby points. If an input recipe gets from A to B in reasonable time, that is a link. The first map came out at 5,318 links. The first bake took 62 minutes, which I learned by watching it take 62 minutes.

## Problem one: omniscience

The first bots knew where you were at all times. My note: "bots need to have sound awareness and not omniscience."

Now they have sight with a field of view and a spot time, they hear noises through walls at reduced range, they call out to each other, and they forget you after eight seconds and go search.

## Problem two: aim

My note: bot aim-down-sights was "impossibly fast."

They had the same ADS time as me. They just also fired halfway through raising the gun, spun at 360 degrees a second and cancelled 100% of their recoil. Now they have a reaction time, they wait for the sights to settle, and they only manage 60% of the recoil. Like the rest of us.

## Problem three: thinking is expensive

"Super laggy," I said. Measured: each bot's path plan spiked 13 ms, and the worst one took 262 ms. A quarter of a second of bot thinking in a 60 Hz game. A proper heap for the pathfinder and a grid for collision fixed that.

## Problem four: the roof

On one map, bots would pick a goal on a rooftop that nothing could actually reach, walk to the nearest wall, and stand there forever, yearning. Fix: prune every nav point the bake never reached.

Related discovery: a staircase with steps 0.356 m tall, on a game where the maximum step is 0.35. Nobody could walk up it. Not bots, not me.

![Kabukicho v6 at night](/blog/gunkhana/kabukicho-v6.jpg)

## Problem five: the bots had a secret life

During a performance audit we noticed the dedicated servers were at 73% and 27% CPU with zero humans connected.

The bots were playing each other. Full matches, around the clock, on a server I pay for by the month. Nobody was watching. Nobody was keeping score. I like to think some of them got pretty good.

The servers now idle when empty.

Next week: getting this thing onto my brothers' computers, which was harder than writing it.
