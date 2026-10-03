<div align="center">

# NoorlandStudios

**The team building NoorlandMC** — a custom Minecraft server with its own economy, jobs, quests, towns, mobs, and world, built as one connected plugin suite.

[![Play](https://img.shields.io/badge/Play-play.noorlandmc.com-4c9a2a?style=for-the-badge)](https://play.noorlandmc.com)
[![Add our server to bedrock](https://img.shields.io/badge/Bedrock-play.noorlandmc.com-4c9a2a?style=for-the-badge)](minecraft://?addExternalServer=NoorlandMC|play.noorlandmc.com:19132)
[![Discord](https://img.shields.io/badge/Discord-Join%20the%20server-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/noorlandmc)
[![Website](https://img.shields.io/badge/Website-noorlandmc.com-2b6cb0?style=for-the-badge)](https://noorlandmc.com)

</div>

---

## Who we are

NoorlandStudios is the development team behind **NoorlandMC**, a Minecraft server running on Paper (Folia-ready) with everything beyond vanilla built in-house: an economy, 14 player jobs, towns and personal camps, custom items and mobs, staff tooling, and a resource pack that generates itself.

None of that is one giant plugin — it's a suite of focused plugins that all plug into a shared core, so features stay decoupled and the server can grow one module at a time. This organization is where that suite lives. Our repositories are private to the team, but this page is the map: what each plugin does, and how they fit together.

Want to see it in action instead? Hop on at **[play.noorlandmc.com](https://play.noorlandmc.com)** or come say hi on **[Discord](https://discord.gg/noorlandmc)**.

## Architecture

Everything routes through **NoorCore**. Satellite plugins never reach into each other's internals — they talk through service bridges registered in NoorCore's registry, so any plugin can be missing without breaking the ones that depend on it.

```
                         ┌─────────────────────────┐
                         │        NoorCore         │
                         │  Service registry & API │
                         │  Event bus              │
                         │  Feature flags          │
                         │  Shared menu framework  │
                         │  Folia-aware scheduling │
                         └────────────┬────────────┘
                                      │ service bridges
        ┌───────────────┬─────────────┼─────────────┬───────────────┐
        │               │             │             │               │
    NoorItems       NoorTowns     NoorEconomy    NoorJobs        NoorPack
    NoorGeodes      NoorQuests    NoorCrates     NoorFish        NoorNPCs
    NoorRanks       NoorAdmin     NoorEvents     NoorChatExtras  ...and more
```

Every plugin in the suite ships `folia-supported: true` and runs on Paper `1.21.11` / Java 21. NoorCore shades a single relocated copy of [FoliaLib](https://github.com/TechnicallyCoded/FoliaLib) so nothing downstream schedules a task the legacy, non-region-aware way.

## The plugin suite

<table>
<tr><td colspan="2"><strong>Backend</strong></td></tr>
<tr><td><strong>NoorCore</strong></td><td>The framework every other plugin builds on — service registry, event bus, feature flags, anticheat, shared GUI framework, Folia-safe scheduling.</td></tr>
<tr><td><strong>NoorMenus</strong></td><td>The server's main menu and a live in-game menu editor.</td></tr>
<tr><td><strong>NoorMisc</strong></td><td>Quality-of-life commands, portal control, horse mounts, and store/announcement hooks that don't need their own plugin.</td></tr>
<tr><td><strong>NoorWeb</strong></td><td>Bridges the server to noorlandmc.com — exposes live market and account data for the site to read.</td></tr>
<tr><td><strong>NoorBot</strong></td><td>Our Discord bot — tickets, transcripts, and moderation tooling for the community server.</td></tr>

<tr><td colspan="2"><strong>Economy & Jobs</strong></td></tr>
<tr><td><strong>NoorEconomy</strong></td><td>The server's currency, with a fully audited transaction history, a player-run commodities market, and an auction house.</td></tr>
<tr><td><strong>NoorJobs</strong></td><td>14 player jobs — miner, farmer, fisher, blacksmith, wizard, and more — with levels, promotions, boosters, and payouts.</td></tr>

<tr><td colspan="2"><strong>Ranks & Rewards</strong></td></tr>
<tr><td><strong>NoorRanks</strong></td><td>The server's progression ladder, from Newcomer up through Imperator.</td></tr>
<tr><td><strong>NoorCrates</strong></td><td>Crates and keys, weighted reward pools, an in-game crate editor, and scheduled deliveries.</td></tr>
<tr><td><strong>NoorSupporter</strong></td><td>Vote rewards and supporter perks.</td></tr>

<tr><td colspan="2"><strong>Towns & NPCs</strong></td></tr>
<tr><td><strong>NoorTowns</strong></td><td>Personal camps and full towns — claims, roles, banks, upgrades, and consent-based wilderness PvP.</td></tr>
<tr><td><strong>NoorNPCs</strong></td><td>Dialogue-driven guide NPCs plus roaming NPCs players can recruit, station, and put to work.</td></tr>

<tr><td colspan="2"><strong>Items, Mobs & World</strong></td></tr>
<tr><td><strong>NoorItems</strong></td><td>Custom items, tools, and armor defined entirely in YAML — no code required — plus custom enchantments and an in-game item/recipe editor.</td></tr>
<tr><td><strong>NoorGeodes</strong></td><td>The tiered fragment → catalyst → geode salvage economy that turns rare drops into rewards.</td></tr>
<tr><td><strong>NoorEntities</strong></td><td>Custom mobs and mannequins with their own modular AI — goals, sensors, and brains.</td></tr>
<tr><td><strong>NoorPack</strong></td><td>Generates the server's resource pack straight from a texture folder — models, item definitions, and a matching Bedrock/Geyser pack, automatically.</td></tr>
<tr><td><strong>NoorPickup</strong></td><td>Folia-safe auto-pickup for item drops, with per-player filters.</td></tr>
<tr><td><strong>NoorFish</strong></td><td>Custom fish, modular rods, and a collection menu, on top of NoorItems.</td></tr>

<tr><td colspan="2"><strong>Quests & Events</strong></td></tr>
<tr><td><strong>NoorQuests</strong></td><td>Daily quests, streaks, and story questlines that tie the server's progression together.</td></tr>
<tr><td><strong>NoorEvents</strong></td><td>Timed seasonal events — token shops, fishing contests, and more.</td></tr>
<tr><td><strong>NoorGames</strong></td><td>Small in-world minigames, starting with Wordle in a chest.</td></tr>

<tr><td colspan="2"><strong>Chat & Community</strong></td></tr>
<tr><td><strong>NoorChatExtras</strong></td><td>Multi-channel chat, custom chat tags, emoji, and moderation tools like slowmode and spy.</td></tr>
<tr><td><strong>NoorFriends</strong></td><td>Friends, parties, and friend teleport.</td></tr>
<tr><td><strong>NoorFamilies</strong></td><td>Guardian controls and chat auditing for linked child accounts.</td></tr>
<tr><td><strong>NoorGuide</strong></td><td>An in-game, staff-curated knowledge base players can search with <code>/question</code>.</td></tr>
<tr><td><strong>NoorAdvancements</strong></td><td>A custom advancement menu replacing vanilla's.</td></tr>
<tr><td><strong>NoorRadio</strong></td><td>On-demand resource-pack music.</td></tr>
<tr><td><strong>NoorMapArt</strong></td><td>Tooling for building and displaying map art.</td></tr>

<tr><td colspan="2"><strong>Moderation</strong></td></tr>
<tr><td><strong>NoorAdmin</strong></td><td>Staff punishment tools built around a reputation-scoring system — infractions, freeze, audit history with undo, and a full moderation GUI.</td></tr>
</table>

## Built with

Java 21 · Paper 1.21.11 · Folia · Vault · Maven

---

<div align="center">

**[play.noorlandmc.com (Java IP)](https://play.noorlandmc.com)** &nbsp;·&nbsp; **[Discord](https://discord.gg/noorlandmc)** &nbsp;·&nbsp; **[noorlandmc.com](https://noorlandmc.com)**

</div>
