# #001 — First two weeks: from template to MVP

**Date:** 2026-10-01 · **Milestones:** M0, M1 · **Tags:** `meta` `vehicle` `survival`

<!-- TODO: GIF of a run from start to finish -->
![](../media/devlog/001-cover.gif)

## TL;DR
In two weeks the project went from the UE5 templates to a playable MVP: a car built from parts, fuel, cold, a trunk and a Lofoten map with a finish line. It now has a new name, **The Last Car**, and this devlog.

## How it went

**26 Aug — start.** The First Person and Vehicle templates are combined into one project. The car model is cut into separate parts in Blender (doors, hood, bumpers, engine, wheels, seats) so that each one can be removed and fitted back.

**Late August — the core.** Parts are fitted to sockets from the `DT_CarObjects` table, with a green/red ghost preview. A single interact key works through the `BPI_Interact` interface. Seats get sockets and occupancy tracking, and the trunk becomes a grid where each item has its own footprint.

**31 Aug — the loop closes.** The jerry can arrives: pick it up, carry it to the car, refuel. From here the game has its core loop: *find → carry → fit or refuel → drive on*.

**10 Sep — MVP map.** The terrain is built from real elevation data of Lofoten, with a road, a finish trigger and an end screen.

**Now.** Body temperature (cold slows you down), stamina, and an interaction rework are in progress.

## What worked
- **Interfaces instead of casts.** The character doesn't know what a door, a wheel or a jerry can is; it calls the interface and the object decides what to do. Adding new items is cheap.
- **Data first.** Part sockets, seats and item footprints all live in tables, so the car can be rebuilt from data. This will pay off for the save system too.

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
