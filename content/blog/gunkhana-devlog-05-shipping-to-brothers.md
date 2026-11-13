---
title: "Gunkhana Devlog 05: Shipping a Game to Exactly Two People"
date: 2026-10-09
tags: ["gunkhana", "devlog", "netcode"]
description: "Netcode, DNS roulette, a patch system, and a 1.2 GB download running at the frame rate."
---

The player base for this alpha is me and my two brothers. That is still enough players to need real netcode, a real server, and a real way to patch the game, so we built all three.

## The netcode

Authoritative server, 60 ticks a second. Clients send their last few inputs, predict their own movement and get corrected by the server. Other players are drawn slightly in the past so they move smoothly, and hits are checked against where the target was when you fired. Bots fill empty seats. Standard stuff, and it all runs through the same headless tests as everything else.

## DNS roulette

First night online, joining by name worked about one time in four.

The domain I pointed at the server had four address records. One was the game server. The other three were left over from a website and pointed at GitHub. Every join attempt was a spin of the wheel, and three of the four slots were a web host that had no idea what a Gunfight was. Deleted three records, fixed.

## "Why do you recommend itch.io?"

The agent suggested distributing builds on itch.io. I asked why, when we already had a game server sitting right there. So it built a patch pipeline instead: every release is a signed patch, the game checks for one at launch, and the server refuses clients on the wrong version.

This worked great until patches hit 557 MB each, because every patch was a diff against an ancient base build. A fresh base brought them down to about 0.4 MB.

## The update that could not be downloaded

Later a 1.2 GB patch went out and my own PC refused to install it. Downloaded twice, timed out twice.

The updater was reading the download one small chunk per drawn frame. On a menu screen ticking along at a low frame rate, the download ran at the speed of the menu. 1.2 GB never had a chance before the ten-minute timeout. With a background thread and bigger chunks, the same download takes 23 seconds.

The cruel part: you can't patch the patcher with a patch the patcher can't download. Old installs needed a full reinstall to get the fix.

![The loadout screen](/blog/gunkhana/loadout.jpg)

## Other bills that came due

- GitHub rejects pushes over 2 GB. Our art history is large. Pushes now go up in chunks.
- The server started at my house. I didn't love opening my home network to the internet, but I also didn't want to make my brothers install VPN software to shoot me. It lives on a rented box now.
- The release button now requires me to say "release it" in my own words. The agent is not allowed to decide the game is ready.

Next week: I ask whether anyone researched how to design an FPS map. The answer was yes, and it hurt.
