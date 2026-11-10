---
title: TurnTimer
aliases:
tags:
  - project
  - coding
  - multiplayer
draft: false
---

A multiplayer chess clock for board games, played across everyone's phones.

**Try it:** [timer.deanw.dev](https://timer.deanw.dev/)

## Why I made this

When we play board games with my friends, we like using a chess clock so nobody takes
forever over their turn. One phone in the middle of the table means everyone keeps
reaching across to tap it. With TurnTimer, every player has the clock on their own phone.

## How it works

- One person creates a lobby and shares the link.
- Everyone opens it, picks a name and joins.
- The host sets the time per player and starts the game.
- You end your turn from your own phone, and the next player's clock starts on every
  screen at once.

Players without a phone can share someone else's device, and the host can pause the
game and adjust anyone's time.

Each lobby runs in its own Cloudflare Durable Object. I wrote about why that's a good
fit here: [[articles/free-backend-for-your-mates-game-lobby|The free backend for your mates' game lobby]].
