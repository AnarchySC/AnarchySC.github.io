---
title: "Gunkhana Devlog 09: Something's Off and I Can't Name It"
date: 2026-11-06
tags: ["gunkhana", "devlog", "game-feel"]
description: "Hunting invisible feel bugs: drifting sensitivity, galloping fire rates, and wrists bent 144 degrees."
---

The worst bug report I ever filed: the game "feels pretty good but theres something off about it. Just slightly I cant name it."

The agent went looking for things a hand would notice and a brain would not. It found six. The top three:

**1. My mouse sensitivity was changing while I ran.** Sensitivity scaled with the camera's field of view, which is right for zooming. But the FOV also widens ten degrees when you sprint and pulses on every shot. So my turn rate drifted 13% depending on how fast I was moving.

**2. The guns galloped.** Shots can only happen on 60 Hz ticks. A gun firing every 0.085 seconds can't land evenly on those, so 17 of 21 automatics fired in a limp: five ticks, five, five, six. Sound, recoil and kick all carried the stutter. Fire intervals are now whole ticks.

**3. The pistols ate clicks.** Click a semi-auto a hair faster than its fire rate and the game threw the click away. One test pistol clicked 20 times and fired 10. Now a press is remembered for 0.15 seconds.

After the fix: "feels waaay better as far as aiming."

## The guns were black

A separate "why does it look cheap" audit found my favourite bug of the project. All 208 weapon colours were being read in the wrong colour space. Every gun in the game was rendering 12.9 times too dark.

![Before and after: the same frame with corrected gun colours and lighting](/blog/gunkhana/guns-dark-before-after.jpg)

## The arms

Four separate times I reported that characters' arms twist up and their hands fold backwards. Three times it was fixed by nudging pose numbers. The fourth time I asked for the why.

The why: the gun-holding code solved where the wrist should be and nothing else. No joint limits. On the home screen poses the elbow was locked straight and the wrist absorbed everything. Measured wrist bend: up to 144 degrees. A human wrist stops around 75.

The agent fixed it, rendered eight characters, and told me they looked like real two-handed holds. I opened the game on the default soldier, who was not in its list of eight. The gun was behind his back. My message: "check out latest screen shots. My question is...you fuckin serious?"

![Arm fix, before and after](/blog/gunkhana/arms-before-after.jpg)

*Left pair before, right pair after, with real motion-captured rifle holds.*

The rule now is to render every body in the roster, defaults included, from the front and the back, and look at every tile before saying anything is fixed.

## Sleeves

Last one. Looking down in first person filled my screen with my own sleeves: up to 18% of the view on the bulkiest character. The first-person body stayed level while the gun followed the camera, so the arms folded up into my face. The torso now tilts with the look.

Next week: the game gets its real name, and a full accounting of everything the robot broke.
