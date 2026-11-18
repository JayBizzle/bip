# Bip

A two-player biplane dogfight for the browser. It's a remake of *Biplane Duel* (a.k.a. "Bip") on the Amiga, which was based on *Biplanes* from the Intellivision *Triple Action* cartridge.

![Bip screenshot](screenshot.png)

## Play

**[Play it online](https://jaybizzle.github.io/bip/)**, or open `index.html` in a browser. Press **Space** to start. There's no build step and nothing to install.

## Bip 3D

**[Play the 3D version](https://jaybizzle.github.io/bip/3d/)**, or open `3d/index.html`. It's a first-person variant: you fly from the cockpit through full 3D, built with [Three.js](https://threejs.org/) and still with no build step. Two players on one keyboard get a split screen, and online play gives each of you your own full-screen cockpit.

| | Climb / dive | Roll | Engine (on/off) | Fire |
|---|---|---|---|---|
| **Player 1** (red, top) | W / S | A / D | Q | Space |
| **Player 2** (blue, bottom) | ↑ / ↓ | ← / → | Right Shift | Enter |

Rolling banks the plane into a turn. The **Pitch** button under the game swaps climb and dive if you prefer flight-sim controls. Brackets show the other plane when it's in view, and an arrow points to it when it isn't. Stalls, gun overheating, crashing into the ground or hut, and runway protection work as in the original. Fly too far out and the plane turns back on its own. The balloon, seagull and parachutes haven't been added yet.

## Online play

Click **Play online** under the game, then send the link it gives you to your opponent. When they open it, either of you presses **Space** to start. Online, you each fly your own plane with either set of keys.

The two browsers connect directly using [PeerJS](https://peerjs.com/). Its free public server only introduces them. The host's browser runs the game, and the other browser sends its controls and draws what the host sends back. The host's tab needs to stay in the foreground, because browsers pause background tabs.

## Controls

| | Throttle (on/off) | Loop back | Loop forward | Fire |
|---|---|---|---|---|
| **Player 1** (red) | W | A | D | S |
| **Player 2** (blue) | ↑ | → | ← | M |

## Rules

- Shoot the other plane down to score. First to 10 wins.
- Hitting the ground or the hut kills you, and your opponent gets the point.
- Fly off one side of the screen and you come back on the other.
- Climb too steeply or let your speed drop and you'll **stall**. The engine coughs and the wings wobble as a warning. Dive to recover.
- Planes on the runway can't fire and can't be hit.
- Your gun **overheats** if you hold fire too long, and jams until it cools.
- When you're shot down your pilot **bails out**. Once the parachute opens, the other player can shoot the pilot (or fly through the chute) for a bonus point.
- Mid-air collisions destroy both planes and score nothing.

## Power-ups

- **Balloon**: it takes 5 hits. The player who pops it gets 3 seconds of **rapid fire** with no overheating. It comes back at a random time and place.
- **Seagull**: shoot it and it squawks and launches a **guided missile** at your opponent. The missile turns slower than a plane, so a tight loop can shake it. It can be shot down, it runs out of fuel after 10 seconds, and it dives into the ground if its target goes down.

## Tuning

All the gameplay numbers (speeds, stall, turn rate, heat, power-up timings) are constants at the top of the script in `index.html`.
