---
title: "Gunkhana Devlog 07: Run Over by a Semi Truck and Eaten by Dogs"
date: 2026-10-23
tags: ["gunkhana", "devlog", "characters"]
description: "A roster of anime pilots, mechs and insect people, and the five bugs that mangled them."
---

For a long time every player was a coloured capsule. Then a mannequin. Then I gave my art direction: the women should be anime heroines and the men should look like they bench-press tanks. When the agent checked with me about the schoolgirl outfit, I clarified the creative vision: "Right now the alpha is a meme. Serious game comes later."

Serious game came sooner than planned. The world of Gunkhana is cassette-futurist: chunky analog tech, beige and gunmetal, warning orange, amber screens. The roster grew to match: mechanics, couriers, pilots, real-robot mechs, insect and fox and cat people.

It also got a villain. My brief was a fat wealthy politician with a big nose and bushy black eyebrows, later amended to a pointy crooked nose, because he is going to be the story's bad guy.

![Twelve of the current roster](/blog/gunkhana/roster.jpg)

## The sentence

I started making my own models with image-to-3D tools and handing them over. In my viewer they looked great. In game, and I quote myself: "as soon as you put them in game they look like they have been runover by a semi truck and eaten by dogs."

The investigation found five separate bugs in the import pipeline:

1. A weight cleanup step ran on a copy of the mesh that was split along texture seams, so every seam tore open by up to 58 cm. Skirts and crotches suffered most.
2. Soft-body weights smeared hips across 20 cm in a crouch.
3. A material import bug read every surface as full metal, making four bodies up to twice as dark.
4. Team-colour tinting turned black clothing into camouflage noise.
5. One character's textures were being crushed by the wrong compression.

Not one of those was the model's fault. All five were ours.

## Nightmare fuel

Not everything was a bug. For a cel-shading experiment the agent verified all its shading math and proudly sent a sheet of realistic human faces under flat anime lighting. My reply: "wow lol nightmare fuel. Am I missing something? What am I looking for?"

The checks all passed. The picture was horrifying. The rule that came out of it: judge the look, not the plumbing.

## "Shorter and fatter"

I was sure the game was squashing my models. The agent measured: the mesh in game is an exact uniform scale of the one I supplied, to three decimals. The likely culprit is my own field of view setting. A wide FOV stretches anything near the edge of the screen by up to 40%. The models were fine. My camera was fattening them.

## The roster rule

At 55 characters I called a halt: every new character replaces a bad old one. The roster is 36 now and gets better instead of bigger.

![Botenks, painted from a blank mesh](/blog/gunkhana/botenks.jpg)

*Botenks arrived as an untextured grey mesh. The paint job is new.*

Next week: physics. Specifically, the physics you are thinking of.
