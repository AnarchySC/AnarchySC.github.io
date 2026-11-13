---
title: "Gunkhana Devlog 08: A Bag of Water on a Stick"
date: 2026-10-30
tags: ["gunkhana", "devlog", "physics"]
description: "Jiggle physics, hair, and writing a cloth solver because springs are not fabric."
---

Gunkhana is rated M and I am going to be an adult about this devlog. Mostly.

My note was that the characters felt stiff, "less mmmm robotic" please. So tails, ears, wings, antennae and skirts got spring bones. Then I asked for the obvious next thing.

The first pass moved the soft parts two centimetres. My review: "i cant see any difference." It was doubled.

## The laboratory

Then I had a theory, and I want it on the record that I delivered it with a straight face. Picture a bag of water on the end of a stick. The stick is mounted to a wall on a ball joint. A spring runs from the bag back up to the wall.

The agent built exactly that as a physics model, on a branch named `jiggle-labs`, with the water sloshing on its own spring. It also informed me, politely, that one spring on a ball joint only resists along its own line, so side to side my design was a swinging gate. Then it rendered three versions side by side.

"OH YEAH labs b is way better!" I said, and we tagged it `jiggle-v2`.

Later I played both and went back to version 1.

There is now an automated test that locks the approved motion, and it will not pass unless my approval is quoted in the commit. This is the most rigorous change control anywhere in the project.

## Springs are not cloth

Springs worked for tails. For clothing they were wrong, and I said so: flowiness needs to depend on thickness, and it shouldn't be a spring "because that just makes the clothes jiggle."

The agent tested everything available for the engine, rejected all of it, and wrote its own cloth solver in C. One knob per garment: thickness in millimetres, which drives weight, stiffness and how the air moves it. A sweatshirt and a cloak are the first two garments on it.

Hair got its own flow sim after an early attempt on one character that, in my words, was fine, though the hair "seems a little big, but that might be because the model has a big head."

## The biggest disappointment

Not everything worked. An attempt to port 697 clothing pieces from a tailoring tool passed every automated check and looked fine in thumbnails. In game, every single piece was broken: see-through backs, puffy shapes, ragged hems. I called it the biggest disappointment I have ever experienced, which was dramatic but felt right at the time.

Same lesson as the nightmare-fuel faces, learned twice: look at a few pieces in the game, in motion, from the front and the back, before you build a pipeline for 697 of them.

![The home screen](/blog/gunkhana/home.jpg)

Next week: something about the game feels off and I can't say what.
