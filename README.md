# Prototype challenges for The Prompt Pit

Prototype challenge builds and starter scaffolds for
[The Prompt Pit](https://github.com/Len-PGH/prompt_pit) — the live vibe-coding
championship control room built for ClueCon.

These were an earlier, self-contained take on the *challenge* half of the event:
each one a real, callable SignalWire agent that contestants had to bend to a goal.
They were split out of the main repo to keep Prompt Pit focused on running the show.

## What's here

### `challenges/` — reference builds

A FastAPI app serving five callable challenges, plus an `/admin` switcher that
repoints a phone number at whichever one is live. Built on the SignalWire Agents SDK.

| Route | Challenge |
|---|---|
| `/worst-ivr` | **Build the Worst IVR** — a working phone tree; make it maximally infuriating and keep it callable |
| `/fix-disaster` | **Fix This Disaster** — SWML with four seeded bugs, easy to hard |
| `/rogue-agent` | **AI Voice Agent Gone Rogue** — prompt-engineer a helpful agent into gradual theatrical collapse |
| `/carrier` | **Carrier-Grade or Chaos?** — answer, look something up over HTTP, branch, connect or fail gracefully |
| `/prompt-golf` | **Prompt Golf** — hit an exact target output in the fewest prompt characters, temperature pinned to 0 |

`configure_number.py` wires a number's voice handler straight to the active
challenge, so there's no dashboard step on event day.

### `scaffolds/` — contestant starting points

One file per challenge — working baselines rather than blank pages, so the clock
is spent on the interesting part.

> `fix-this-disaster.SOLUTION.yaml` is **host and judge only**. It documents the
> four seeded bugs. Don't hand it to contestants.

## Running it

```bash
cp challenges/.env.example challenges/.env   # fill in your SignalWire details
./challenges/run.sh
```

Needs a SignalWire space, project and token, and a number to demo on. The SWML
webhooks sit behind basic auth, generated on first run if you leave it blank.

## Provenance

Extracted from `Len-PGH/prompt_pit` at commit `c890751`, with history preserved.
Prototype code — kept for reference, not actively maintained.
