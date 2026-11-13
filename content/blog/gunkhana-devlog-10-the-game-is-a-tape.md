---
title: "Gunkhana Devlog 10: The Game Is a Tape"
date: 2026-11-13
tags: ["gunkhana", "devlog", "ui"]
description: "A name, a cassette-futurist interface, traps, and an honest list of everything the robot broke."
---

For most of its life this game was called "gunfight", which is also the name of the mode it borrows from someone else's game. I floated **Gunkhana**, from gymkhana, and worried it was too niche. The agent argued for keeping it: it fits a game about stunts and movement, and "khana" means house, so it reads as gun house. The risk is people reading it as "gunk." We kept it anyway.

## The Deck

The first interface pass was tasteful gunmetal. I said: "You can push it further. Cassette Futurism is the aesthetic we are going for," and sent pictures of cassette J-cards and VHS sleeves. Flat colour, stripe bands, huge numerals.

The current design is called The Deck. The game is a tape, the menus are its J-card, and a match is a recording. The five-colour stripe is a legend that means the same thing on every screen: red is danger to you, mustard is reward, cream is print, teal is live values, deep teal is locked. Finished matches go on a shelf as tapes.

![The Deck home screen](/blog/gunkhana/home.jpg)

Also new lately: traps (proximity mines, teleporter pads, laser mines, an EMP, a tether that yanks you back; I played the placeholder version and my review was "I love it lol"), team colours picked by the captain, a ranked mode, and a soundtrack that is now four of my own songs.

## Things the robot broke

In the interest of honesty, a partial list:

- **My entire desktop.** A texture script multiplied two arrays the wrong way, reached 56 GB of RAM, and the system killed everything, including the agent. My message when it came back: "You crashed! it said device memory full."
- **My credits.** Six agents working in parallel burned through the usage allowance in 33 minutes. All six died mid-task with nothing committed. It had just told me the job would take about three hours. I asked, "are you sure?"
- **My settings.** Automated tests kept overwriting my real settings file.
- **My sound.** See devlog 03.
- **Itself.** Twice in one session it ran a command to kill a stuck process that also matched its own shell. It killed itself. Twice.
- **A character rig.** After several rounds of hand-built rigging on one model, my review was that it "cannot go in the game." Rigging goes to proper tools now.

Each of these became a written rule the agent reads at the start of every session. That is the real workflow: I play, I complain in plain words, the complaint becomes a measurement, the measurement becomes a fix, and the mistake becomes a rule.

## Where it stands

About 1,900 automated tests. Over a thousand commits. 36 characters, 16 maps, 2v2 and 5v5. By my own estimate the game is about 60% done, which in game development means the remaining 40% will take the other 90% of the time.

More soon.
