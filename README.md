# Broken Highway — Antigravity Arc Jumper (AJX-704 Edition)

A playable real-time arcade game in Python, built with nothing but the standard
library (`tkinter`, `math`, `random`, `time`). No engine, no third-party
packages: the physics, the render loop and the game state machine are all
written out by hand.

You pilot the AJX-704 — an X90 Toyota Mark II, the 1JZ-GTE car — along a broken
elevated highway, jumping the gaps it tears open. One life. Fall and it is over.

## Run it

Needs Python 3 with `tkinter` (included in the python.org installer on Windows).

```
cd "ICT project/brokenHighway"
python main.py
```

`main.py` opens a resolution picker, then the game window. **SPACE** jumps;
**SPACE** again in mid-air is the second jump.

## What is in here

| Path | What it is |
| --- | --- |
| `ICT project/brokenHighway/` | The game, split into nine modules |
| `.../main.py` | Entry point: resolution picker, window, loop |
| `.../game.py` | State machine, scoring, difficulty curve |
| `.../physics.py` | Gravity, velocity tracking, AABB collision at gap edges |
| `.../entities.py` | The car, gap geology, particles |
| `.../parallax.py` | Seven-layer parallax sunset, sun/moon, generated skyline |
| `.../ui.py`, `assets.py`, `audio.py`, `config.py` | HUD, generated art, sound, tunables |
| `ICT project/DOCUMENTATION.txt` | Full write-up: problem statement, mechanics, module map, scoring maths |
| `ICT project/PRESENTATION_SCRIPT.txt` | The lab presentation script |
| `ICT project/Project_Presentation.pptx` | The slide deck |
| `ICT project/raptor.flowchart.rap`, `raptor.png` | Game-loop flowchart, source and image |

## Scoring

```
distance_score = total_frames * 0.5
gap_bonus      = gaps_cleared * 100
total_score    = int(distance_score) + gap_bonus
```

The best score is written to `highscore.txt`.

## Why it exists

An ICT lab project: implement kinematics, a non-blocking 60 FPS render pipeline
and a finite state machine in a GUI toolkit that was never designed for games,
with no engine available to hide the difficult part.

Viewing only — see `LICENSE`.
