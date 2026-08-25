<div align="center">

# NoorlandStudios

**The team building NoorlandMC** — a custom Minecraft server with its own economy, quests, mobs, items, and world.

[![Play](https://img.shields.io/badge/Play-play.noorlandmc.com-4c9a2a?style=for-the-badge)](https://play.noorlandmc.com)
[![Discord](https://img.shields.io/badge/Discord-Join%20the%20server-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/noorlandmc)
[![Website](https://img.shields.io/badge/Website-noorlandmc.com-2b6cb0?style=for-the-badge)](https://noorlandmc.com)

</div>

---

## Who we are

NoorlandStudios is the development team behind **NoorlandMC**, a Minecraft server running on Paper/Folia. Everything the server does beyond vanilla Minecraft — jobs, custom items, quests, custom mobs, staff tools, even the resource pack — is built in-house as a suite of plugins that all plug into one shared framework.

This organization is where that suite lives. The repositories here are private to the team, but this page is the map: what each plugin does, and how they fit together.

Want to see it in action instead? Hop on at **[play.noorlandmc.com](https://play.noorlandmc.com)** or come say hi on **[Discord](https://discord.gg/noorlandmc)**.

## The plugin suite

Every plugin below depends on **NoorCore**, the shared framework that ties the server together — a service registry other plugins publish and consume from, a feature-flag system, an async event bus, and Folia-aware task scheduling so the whole suite runs on a regionised server without extra work.

| Plugin | What it does |
|---|---|
| [**NoorCore**](https://github.com/NoorlandStudios/NoorCore) | The foundation every other plugin builds on: cross-plugin service registry, feature flags, event bus, anticheat (movement/combat/inventory/interaction tracking), and Folia-compatible scheduling. |
| [**NoorItems**](https://github.com/NoorlandStudios/NoorItems) | Custom items and enchantments, starter kits, an in-game item editor, collections, and tiered loot drops. |
| [**NoorEntities**](https://github.com/NoorlandStudios/NoorEntities) | Custom mobs and mannequins, built on a modular AI system (goals, sensors, brains) for behavior that goes beyond vanilla mob AI. |
| [**NoorJobs**](https://github.com/NoorlandStudios/NoorJobs) | The server's job and economy system — 14 jobs (miner, farmer, fisher, blacksmith, wizard, and more), promotions, boosters, and payouts through Vault. |
| [**NoorQuests**](https://github.com/NoorlandStudios/NoorQuests) | Daily quests, streaks, and story questlines that tie the server's progression together. |
| [**NoorFish**](https://github.com/NoorlandStudios/NoorFish) | A dedicated fishing system with a fish collection menu, layered on top of NoorItems. |
| [**NoorAdmin**](https://github.com/NoorlandStudios/NoorAdmin) | Staff tooling: a reputation/infraction scoring system, freeze-and-review, full audit history with undo, and an in-game GUI for moderation. |
| [**NoorPack**](https://github.com/NoorlandStudios/NoorPack) | Generates the server's resource pack automatically from a texture folder — models, item definitions, and even a matching Bedrock pack for Geyser players — no manual pack config required. |

## Built with

Java · Paper / Folia · Vault · Maven

---

<div align="center">

**[play.noorlandmc.com](https://play.noorlandmc.com)** &nbsp;·&nbsp; **[Discord](https://discord.gg/noorlandmc)** &nbsp;·&nbsp; **[noorlandmc.com](https://noorlandmc.com)**

</div>
