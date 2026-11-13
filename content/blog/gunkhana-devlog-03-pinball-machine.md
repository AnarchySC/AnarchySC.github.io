---
title: "Gunkhana Devlog 03: The Sounds Are Like a Pinball Machine"
date: 2026-09-25
tags: ["gunkhana", "devlog", "audio"]
description: "What happens when the thing building your game's audio has no ears."
---

My request was six words: "gonna need some sound."

The agent came back with 200 public-domain sounds: real recordings of 23 firearms, impacts, reloads, interface clicks, a city-at-night bed. It told me up front it could not listen to any of it. It had checked the files by peak level and onset timing only, and asked me how they sounded.

My review, in full: "LOL the sounds are like a pinball machine."

The gunshots were fine. Everything else (footsteps, hits, reloads) was bright little dings and clacks from UI packs, plus what I suspect were stapler and tape-measure recordings standing in for gun handling. Out they went, replaced with duller synthesized foley. The guns stayed real.

![In-game HUD on the Maglev Line map](/blog/gunkhana/hud.jpg)

## Numbers instead of ears

Later I said the audio was "kinda off. Footsteps and directional audio need work." Since the agent still can't hear, it recorded the game's output and measured it. It found:

- The engine's stereo panner, at our settings, made the far ear **completely silent** at 90 degrees. A sound at 30 degrees in front and 150 degrees behind were identical. That was the "one ear" feeling.
- A running enemy's footstep at six metres sat 39 dB under a gunshot. You were never going to hear anyone coming.
- The master bus had no limiter at all.

The fix was a small binaural setup: 36 audio buses that fake the time delay and head shadow between your ears, and footsteps that land on the animation's actual foot contact. All tuned by measurement, all marked in the design doc as assumptions until I listen.

## The day the game went silent

After that pass I launched the game and heard nothing. No music, no guns. On every branch.

The cause was not the game. Weeks earlier, automated test runs had been blasting menu music through my earphones while I worked, so a helper script muted those test runs at the system level. The sound server helpfully remembered "the app called gunfight is muted" forever, including when I was the one playing it.

Rule now: test runs use a dummy audio driver. Nothing ever touches the system mixer.

## One more lesson

For a stunt cue the agent commissioned a bright, punchy brass stab so it would be easy to place. Bright and punchy is exactly what makes you want to throw your headphones after the fortieth time. Sounds you hear constantly should be soft, warm and short. We cut the cues from one of my own songs instead.

Next week: the bots, who started out as gods.
