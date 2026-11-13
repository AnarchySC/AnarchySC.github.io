---
title: "Gunkhana Devlog 06: One Lane, Zero Flanks"
date: 2026-10-16
tags: ["gunkhana", "devlog", "level-design"]
description: "Six versions of one map, sixteen maps across history, and why it all looked like Roblox."
---

The first map is Kabukicho, a Tokyo nightlife block, because boxy buildings suit box collision and neon looks good on anything.

Version 1, my review: "super simplistic and not conducive for clever and skill based gameplay."

Version 4 was bigger, because I complained that "we automatically know where the enemy is." Bigger did not help.

So I asked: "Did you research level design and making the perfect FPS arena?" And then: "Remember, this is a 2 vs 2 map."

## The autopsy

The agent measured version 5 from 2,163 standing spots, and the report was brutal:

- 99% of the fastest routes crossed the middle on the same street. It was a one-lane map wearing a three-lane costume.
- One single spot could watch all nine enemy routes.
- Teams saw each other a median 2.25 seconds into a 60-second round.
- 38% of the floor got almost no traffic. I had built a parking lot.

It offered a quick patch or a proper rebuild. I said I would rather have it done correctly than fast. Version 6 has a bent street, three lanes split by buildings too tall to see over, and a rooftop that 17,280 brute-force parkour attempts failed to reach. That one shipped.

## Sixteen maps

My map list covers three eras: ancient Greece, a French chateau, 1930s Berlin, a dinosaur jungle, a mountain temple; an Afghan village, a small Alaska town, downtown Houston, Seattle; a space station, a megacity, battle wreckage, a city in an asteroid. My instruction was "just cook until you cant cook anymore."

Highlights from the kitchen:

- The first Afghan village was rejected by the agent itself. A helper had copied version 6's floor plan, numbers and all, and put mud walls on it.
- A decorative skylight ring turned out to be a solid disc. The skylight was closed.
- All sixteen got baked lighting and went into the post-match vote: three random maps, pick one.

![Four maps: Hanabashi Canal, Capsule Yokocho, Undercroft Terminal, Megacity](/blog/gunkhana/maps.jpg)

*Hanabashi Canal, Capsule Yokocho, Undercroft Terminal, Megacity.*

## The Roblox problem

They played fine. They looked like Roblox. My diagnosis after staring at review sheets: the layouts are mostly OK, the textures are the problem.

Photo textures helped. Then the agent tried generating detail with scripts: panels, vents, storefronts, awnings. My response to that one was "This isnt working. You dont seem to understand what I am going for."

Three attempts at code-made level art, three failures. The lesson is now a rule: scripts make simple shapes and plumbing. Detail comes from assets made by artists, placed by a human. So I started blocking out my own map in Blender, a flying island with a commons court, and the agent converts it. It also once tried to texture that map with a script that ate 56 GB of RAM and took my whole desktop down with it. We don't talk about that. (We do. It's in devlog 10.)

Next week: characters, and the worst sentence I have ever typed about a 3D model.
