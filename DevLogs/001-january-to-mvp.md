# #001 — January to MVP: how it got here

**Date:** 2026-10-01 · **Milestones:** M0, M1 · **Tags:** `meta` `vehicle` `survival`

<!-- TODO: GIF of a run from start to finish -->
![](../media/devlog/001-cover.gif)

## TL;DR
The idea appeared in January 2026. Spring went into learning Unreal and building the foundation: parts that come off and go back on, and a car that drives. Over the summer that turned into a playable MVP with fuel, cold, a trunk and a Lofoten map with a finish line. The project now has a new name, **The Last Car**, and this devlog.

## How it went

**January — the idea.** One car, winter, and a group of friends who have to keep it running. Development started straight away.

**Spring — learning while building.** Not much free time between university and a still-new engine. The car model is cut into separate parts in Blender (doors, hood, bumpers, engine, wheels, seats), and the first key system appears: attaching and detaching parts to sockets with a ghost preview. The car drives, but you can't get in yet. By the start of summer that was it: attach/detach, driving and a few small things.

**Summer — the main push.** With more time and a better grip on Unreal, most of the game came together:
- seats, getting in and out, separate input contexts for driver and passengers;
- one interact key for everything through the `BPI_Interact` interface;
- parts described in the `DT_CarObjects` table;
- a grid-based trunk where each item has its own footprint;
- fuel with a consumption curve, and **31 August** the jerry can: pick it up, carry it to the car, refuel. From here the game has its core loop: *find → carry → fit or refuel → drive on*;
- body temperature (cold slows you down) and stamina.

**10 September — MVP map.** The terrain is built from real elevation data of Lofoten, with a road, a finish trigger and an end screen.

## What I learned
- **Interfaces instead of casts.** The character doesn't know what a door, a wheel or a jerry can is; it calls the interface and the object decides what to do. Adding new items is cheap.
- **Data first.** Part sockets, seats and item footprints all live in tables, so the car can be rebuilt from data. This will pay off for the save system too.
- **Spring was not wasted.** Progress looked slow, but the attach/detach system built then is what everything else in the summer was built on.

## What's next (M2)
- [ ] A proper co-op pass: parts, trunk and seats must be the same for every client
- [ ] Physics Prediction for the car (async physics at a fixed 60 Hz is already on)
- [ ] Battery and oil freezing
- [ ] Survival UI synced across players
- [ ] First Blueprint excerpts on blueprintUE

## Why the rename
MyWinterDrive was a working title from the time when this was a sandbox for learning Chaos Vehicles. The idea grew into "one car is everything you have", and the name had to follow.

---
← [All entries](README.md)
