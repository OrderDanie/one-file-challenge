# PIXEL DRIFT COURIER

A top-down pizza-delivery driving game where the rent is due, the pizza is hot, and the police have taken your driving style personally.

![drift. deliver. get fined.]

## Quick start

1. Download `index.html`. The **entire game** is this one file. The whole city lives in it. It's haunted, but in a good way.
2. Double-click it.
3. Press `ENTER` and go to work, blud.

That's it. No `npm install`. No `node_modules` black hole eating 400MB. No yarn, no pnpm, no tears.

## Features

- **Delivery economy** — haul pizza, burgers, sushi and extremely fragile cakes to procedurally-generated houses before they go cold. Late = pay cut. Capitalism, baby.
- **A real GPS that doesn't lie** — A* pathfinding draws a glowing blue route *on the actual roads*, plus a rotating rectangular minimap with north-up toggle (`N`), edge arrows, and metro stations.
- **City Races** — take the *second* highway west to the Raceway district, press `E` on the checkered pad, and drag-race an AI rival to a house. The rival genuinely drives the route and rubber-bands, so your ego is always in danger.
- **13 cars**, including the legendary **Tofu Trueno AE86**. Initial D approved. Tofu not included.
- **Wanted system** — ram traffic and the MPD comes for you. 3 stars summons a helicopter. Getting busted fines you real money and real feelings.
- **A living city** — day/night cycle, rain, fog, lightning, puddles that make you slip, traffic that stops at red lights, pedestrians that fear you, and street lamps that glow.
- **5 synth radio stations** generated live by math. The music is math. The math slaps.

## Run it locally

**Requirements:** a browser from this decade. That's the whole list.

```bash
# option A (recommended): just open the file
double-click index.html

# option B (fancy): serve it
python -m http.server 8000
# then visit http://localhost:8000
```

No language versions. No system deps. No env vars. No database. Your progress autosaves to `localStorage` — clearing browser data gives the game amnesia, which is also a great way to escape your debts. We don't judge.

## How it works (the nerd part)

Everything — city, cars, sprites, music — is generated in code at runtime. There are **zero image assets and zero audio files**. The city is built from a bent street grid, which means the GPS can't cheat with straight lines: it builds a graph of every intersection and runs **A\*** over it ~every 0.4s, then densifies the path along road centerlines so the blue line hugs the curves like it pays rent there.

The race AI uses the *same* pathfinding to drive to the target house, with rubber-banding tuned so races stay close enough to be stressful. The renderer is a low-res canvas upscaled with `image-rendering: pixelated` for the crunchy CRT look, topped with scanlines and a TV-power-on boot animation. Audio is fully synthesized Web Audio: the engine is oscillators pitched to your speed, thunder is filtered noise, and the radio stations are tiny step-sequencers. Your speakers are a chiptune band now.

## Credits

- **Fonts:** *Press Start 2P* & *VT323* via Google Fonts — the only external request, we promise.
- **Art:** none. Every pixel is `fillRect`'d by hand, with love and mild sleep deprivation.
- **Initial D**, for the AE86 and for teaching us that headlights are a weapon.
- **Every real pizza courier** who's ever been asked "can you hurry up?" — this is for you.
- **The traffic AI**, which learned to obey red lights and still gets rammed by you anyway. We're sorry, little guy.

## FAQ

**Is the city real?** No. It's three cities, two highways, and a dream.
**Can I pet the pedestrians?** They will run away. Trust issues.
**The pizza arrived cold.** Skill issue (yours).
**Is the AE86 worth $9,000?** It drifts like it's got something to prove. Yes.

---

*No pizzas were harmed in the making of this game. Several traffic cones were.*