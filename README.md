<p align="center">
  <img src="https://img.shields.io/badge/version-1.6.0-blue?style=for-the-badge" alt="Version">
  <img src="https://img.shields.io/badge/license-permanent%20all--servers-success?style=for-the-badge" alt="License">
  <a href="https://discord.gg/YOUR_REAL_INVITE_CODE"><img src="https://img.shields.io/badge/support-24%2F7%20discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord"></a>
  <a href="https://mc.hypeland.org"><img src="https://img.shields.io/badge/demo-mc.hypeland.org-orange?style=for-the-badge" alt="Demo Server"></a>
</p>

<h1 align="center">ThePit</h1>

<p align="center"><strong>The definitive PvP arena plugin inspired by the Hypixel Pit.</strong></p>

# ThePit

**Production-grade Pit PvP for Minecraft 1.8.8 (Spigot / Paper).**
Engineered for networks that demand deep progression, relentless combat, and zero-compromise performance.
Built from the ground up with a MongoDB + Redis storage backend, an event-driven arena framework, a 28-perk economy, and full cross-server synchronisation — every system exists because competitive Pit servers demanded it.

---

## Table of Contents

- [Test Server – Try Before You Buy](#test-server--try-before-you-buy)
- [Why ThePit?](#why-thepit)
- [Competitive Comparison](#competitive-comparison)
- [Why Exclusively 1.8.8?](#why-exclusively-188)
- [Performance Engineering at a Glance](#performance-engineering-at-a-glance)
- [Core Features – Expanded](#core-features--expanded)
- [28 Perks – Full Breakdown](#28-perks--full-breakdown)
- [Prestige System](#prestige-system)
- [Economy – Gold & Renown](#economy--gold--renown)
- [Events – Major & Minor](#events--major--minor)
- [Bounties](#bounties)
- [Contracts](#contracts)
- [Non-Permanent Items Shop](#non-permanent-items-shop)
- [Permanent Upgrades](#permanent-upgrades)
- [Trade System](#trade-system)
- [Arena Systems](#arena-systems)
- [NPCs](#npcs)
- [Scoreboard & Tab List](#scoreboard--tab-list)
- [Holograms](#holograms)
- [Enderchest](#enderchest)
- [Chat Options](#chat-options)
- [Custom Spawn Positions](#custom-spawn-positions)
- [Player Sync (Cross-Server)](#player-sync-cross-server)
- [Commands & Permissions](#commands--permissions)
- [Full Configuration](#full-configuration)
- [PlaceholderAPI Integration](#placeholderapi-integration)
- [Database & Storage](#database--storage)
- [Diagnostics](#diagnostics)
- [Public API](#public-api)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Support & Purchasing](#support--purchasing)

---

## Test Server – Try Before You Buy

A live, fully functional demo server is available so you can evaluate ThePit before making any commitment.

```
IP: mc.hypeland.org
```

The test server runs the latest stable build with every system enabled. You can experience the full perk arsenal, prestige progression, bounty hunts, scheduled events, the trade system, and every other mechanic exactly as your players would. **No registration, no whitelist — connect and play immediately.**

---

## Why ThePit?

ThePit is not a generic PvP plugin with a few extra commands. It is a complete, self-contained Pit arena solution engineered for networks that cannot afford downtime, data loss, or shallow gameplay.

### The Only Plugin That Truly Unifies the Pit

Every system you need — from prestige progression and a 28-perk arsenal, to a dual-currency economy, scheduled major and minor events, bounty hunts, contracts, a trade system, and full cross-server synchronisation — lives inside **one JAR**. You never install extra modules, you never pay for separate add-ons, and you are never left debugging incompatibilities between half a dozen plugins. ThePit ships with everything integrated and sharing the same configuration system, database layer, and event bus.

### Deep Progression That Keeps Players Hooked

The prestige system lets players reset their level in exchange for permanent prestige tiers and renown — a second currency spent on prestige perks and permanent upgrades. With 14 standard perks unlocked by leveling and 14 prestige perks unlocked through prestiging, players have dozens of meaningful build options. Contracts provide repeatable objectives with gold and XP rewards, giving players a reason to log in every day. This is not a flat PvP arena — it is a progression-driven experience.

### Built for Networks, Not Just Single Servers

ThePit was designed for multi-server deployments from day one. Redis-powered cross-server sync lets multiple arena servers share player progression in real time. When a player earns gold on one server, their balance is instantly reflected on every other server in the network. The sync layer uses Redis pub/sub for live updates and MongoDB for persistence, so data is always consistent — even if a server crashes mid-sync.

### Extreme Performance, Not an Afterthought

Performance is treated as a first-class feature. All database operations run asynchronously on dedicated thread pools, so the main server thread is never blocked by I/O. Player data is loaded lazily on first access and cached for the duration of the session. Scoreboard updates are batched and change-driven. Hologram refreshes are deferred to avoid main-thread pressure. The built-in tick monitor lets administrators diagnose lag spikes in real time. The result is a plugin that maintains a solid 20 TPS even under heavy combat.

### Zero Recurring Costs, True Unlimited License

One payment grants you a permanent license that covers **all servers you own** — whether you run a single arena or a 50-server BungeeCord network. There are no monthly fees, no per-server charges, and no hidden costs. You receive all future updates for the current major version free of charge.

### Direct Access to the Developer

When your server has an issue at peak time, you do not file a ticket and wait. You speak directly to the person who wrote the code. Support is available **24/7** through Discord or Bale, and every report is treated with the urgency that a live production network demands.

## Competitive Comparison

| Criteria | **ThePit** | Hypixel Pit (reference) | Generic PvP Plugins | Other "Premium" Pit |
|----------|-----------|------------------------|--------------------|--------------------|
| **Prestige system** | Full multi-tier with renown currency, prestige perks, and configurable requirements | Yes (proprietary) | Not available | Basic or missing |
| **Perk count** | 28 (14 standard + 14 prestige) | ~30 (proprietary) | 0–5 | Usually under 10 |
| **Dual economy** | Gold (session) + Renown (permanent) | Yes (proprietary) | Single currency | Often gold-only |
| **Database backend** | MongoDB + Redis (cross-server sync) | Proprietary | Flat file / MySQL | Usually MySQL or flat file |
| **Cross-server sync** | Native Redis pub/sub + MongoDB | Proprietary | Not available | Rare |
| **Scheduled events** | 3 major + 5 minor, fully configurable | Yes (proprietary) | Not available | Limited |
| **Bounty system** | Auto-bounty on killstreaks + manual admin bounties | Yes (proprietary) | Not available | Basic |
| **Contracts** | Repeatable objectives with progress tracking and rewards | Yes (proprietary) | Not available | Rare |
| **Trade system** | Full player-to-player trading with double-confirmation | Yes (proprietary) | Not available | Rare |
| **NPC system** | 5 interactive NPCs (stats, prestige, upgrades, shop, contracts) | Yes (proprietary) | Not available | Basic |
| **PlaceholderAPI** | 18+ placeholders, fully integrated | N/A | Varies | Partial |
| **Public API** | Full Java API with 13+ custom events | N/A | Varies | Rare |
| **Setup experience** | Interactive GUI walkthrough + CLI | N/A | Manual | Mostly manual |
| **License model** | Permanent, all servers | N/A | Varies | Often recurring or per-server |

**Key takeaway:** ThePit is the only option that delivers the full Hypixel Pit experience — deep progression, dual economy, cross-server sync, scheduled events, and professional support — in a single purchase that covers every server you run.

---

## Why Exclusively 1.8.8?

Targeting a single version is an intentional engineering choice that guarantees stability and maximum speed.

1. **Performance that newer versions cannot match.** The 1.8.8 server tick loop is leaner, the entity count is lower, and the combat model is simpler. This allows ThePit to employ precise combat calculations, custom entity handling, and version-specific packet interception written directly against the server internals.
2. **No compromises in version-specific integration.** The plugin interacts with `net.minecraft.server` classes directly through ProtocolLib and ViaVersion abstractions. Supporting multiple versions would mean removing these precise, performance-critical hooks.
3. **Stability through predictability.** One version means one test environment. Every feature is verified on clean 1.8.8 Spigot and Paper builds. There are no surprises from API changes or edge cases introduced by newer mechanics.
4. **The competitive PvP standard.** The largest Pit networks built their foundations on 1.8.8. The combat mechanics, knockback calculations, and hit-timing behaviour that competitive players expect are tied to this version. ThePit is built for the version those players demand.

If future versions are supported, they will be delivered as separate, equally optimised branches — never as a bloated, one-size-fits-all JAR.

---

## Performance Engineering at a Glance

ThePit treats performance as a core feature. The following architectural decisions ensure stable 20 TPS even under heavy combat load.

- **Fully Asynchronous Database Layer** – every MongoDB interaction runs off the main thread using dedicated async tasks. Player data is loaded once at join (asynchronously) and cached in-memory for the session. Writes are always flushed off the main thread, so scoreboard, tab list, and chat formatting never block the server tick.
- **Redis L2 Cache for Cross-Server** – when cross-server sync is enabled, Redis pub/sub delivers live updates without polling. The sync layer subscribes to per-player channels and pushes updates only when data actually changes, eliminating unnecessary network traffic.
- **Lazy Data Loading** – player documents are loaded from MongoDB only on first access, not at join time. Events that fire while data is still loading are counted or skipped gracefully instead of throwing errors.
- **Batched Stats Updates** – the `StatsUpdater` accumulates stat mutations and flushes them to MongoDB every minute in a single batch, reducing write pressure by orders of magnitude.
- **Change-Driven Scoreboard** – the scoreboard is rebuilt and sent to clients only when underlying data changes. Idle periods produce zero scoreboard traffic. A per-player objective avoids the flicker that comes with shared objectives.
- **Deferred Hologram Updates** – hologram refreshes are offloaded to avoid main-thread pressure during high-activity moments.
- **Conditional Listener Registration** – listeners are registered only for enabled features. Disabled features consume zero CPU cycles.
- **Map Recovery Tracking** – all blocks placed or broken by players are tracked in memory and reverted on arena reset or server restart, with zero disk I/O for the tracking layer.
- **Built-in Tick Monitor** – a lightweight diagnostic tool that prints a console warning whenever the main thread's tick duration exceeds a configurable threshold (default 100 ms), making it trivial to identify and eliminate lag spikes.

---

## Core Features – Expanded

### Complete Pit Mechanics

Every core mechanic is implemented in full detail: a closed PvP arena where players fight, earn gold and XP from kills and assists, prestige to unlock permanent perks and renown, and participate in scheduled events. The golden head reward system uses a strict streak gate — kills 1 and 2 yield nothing, kill 3 yields the first golden head, and every subsequent kill yields another — preventing snowballing and rewarding consistent combat. Dying resets the kill counter, so players must earn their way back.

### Deep Player Progression

Every player who joins the arena gets a persistent MongoDB document containing their level, XP, prestige, gold, renown, bounty, perk selections, perk slots, comprehensive stats (kills, deaths, assists, damage dealt/taken, blocks placed/broken, arrows shot/landed, time played), chat options, and enderchest contents. This data is loaded lazily, cached in-memory, and flushed asynchronously on disconnect.

### 18 Specialised Managers

ThePit's codebase is organised around 18 dedicated managers, each responsible for a single domain:

| Manager | Responsibility |
|---------|---------------|
| `PlayerManager` | Player data loading, caching, and session lifecycle |
| `CombatManager` | Combat tag tracking and damage flow |
| `StreakManager` | Kill-streak tracking, golden head eligibility, and bounty threshold |
| `EntityManager` | Custom entity spawning and version-aware abstraction |
| `RegionManager` | Spawn protection, pit hole, and event regions |
| `BlockManager` | Block placement tracking for map recovery |
| `MapRecoverManager` | Automatic reversion of player-placed blocks |
| `RandomGoldManager` | Timed gold ingot spawns at configured positions |
| `HologramManager` | Lightweight hologram system (static + refreshable) |
| `HotbarManager` | Automatic hotbar restoration on respawn |
| `EnderchestManager` | Persistent, per-player enderchest storage |
| `TabListManager` | Custom tab list header, footer, and level-prefix sorting |
| `ScoreboardManager` | Per-player, change-driven scoreboard with event status sync |
| `SoundManager` | Centralised sound effect routing |
| `WorldManager` | Arena world loading and lobby border management |
| `LobbyBorderManager` | Lobby boundary enforcement |
| `GlobalManager` | Cross-system coordination and plugin state |
| `TickMonitorManager` | Main-thread tick duration monitoring and warning |

---

## 28 Perks – Full Breakdown

The perk system has two tiers. Players have a fixed number of perk slots and can equip any combination of unlocked perks.

### Standard Perks (14) — Unlocked by Leveling

| Perk | Effect |
|------|--------|
| **Bounty Hunter** | Earn bonus gold when killing a player who has a bounty |
| **Endless Quiver** | Arrows are never consumed when shooting a bow |
| **Fishing Rod** | Pull players toward you with a fishing rod |
| **Gladiator** | Gain bonus damage reduction for each nearby enemy |
| **Golden Heads** | Golden apples heal more and apply Regeneration |
| **Lava Bucket** | Spawn with a lava bucket that refills on kill |
| **Lucky Diamond** | Small chance to find diamonds when mining |
| **Mineman** | Mine blocks faster in the arena |
| **Safety First** | Reduced damage from the first hit taken in combat |
| **Spammer** | Reduce cooldown on non-permanent items |
| **Streaker** | Gain bonus gold for each kill while on a killstreak |
| **Strength Chaining** | Gain Strength on kill for a short duration |
| **Trickle Down** | Allies near you gain a portion of your gold income |
| **Vampire** | Heal a percentage of damage dealt |

### Prestige Perks (14) — Unlocked by Prestiging + Renown

| Perk | Effect |
|------|--------|
| **Assist Streaker** | Assists extend your killstreak timer |
| **Barbarian** | Bonus melee damage at low health |
| **Co-op Cat** | Share perk effects with nearby teammates |
| **Conglomerate** | Earn passive gold over time |
| **Dirty** | Inflict Weakness on the player you hit |
| **First Strike** | Bonus damage on the first hit against a fresh opponent |
| **Kung Fu Knowledge** | Reduced fall damage and increased jump height |
| **Marathon** | Speed boost after running for a few seconds |
| **Olympus** | Reduced incoming projectile damage |
| **Overheal** | Excess healing becomes temporary absorption |
| **Rambo** | Bonus damage when fighting multiple enemies at once |
| **Recon** | See nearby player health bars |
| **Soup** | Mushroom stew heals instantly like golden apples |
| **Thick** | Flat damage reduction against all sources |

---

## Prestige System

The prestige system is the backbone of long-term player retention. Players who reach the maximum level can reset their level back to 1 in exchange for one permanent prestige level and a chunk of renown — a second currency that persists across prestiges and is never reset.

- **Prestige Tiers** – each prestige level unlocks new prestige perks and increases the player's prestige tier, displayed in chat and on the scoreboard.
- **Renown Economy** – renown is earned exclusively through prestiging. It is spent on permanent prestige perks and permanent upgrades that are always active and do not occupy a perk slot.
- **Configurable Requirements** – minimum level requirement, renown reward per prestige, and tier thresholds are all defined in `Prestige.yml`.
- **Prestige NPC GUI** – players self-prestige through an in-game GUI at the Prestige NPC. The interface shows current progress, requirements, and rewards clearly.
- **Admin Control** – `/thepit prestige <set/add/take> <player> <amount>` lets administrators manage prestige levels for any player.

---

## Economy – Gold & Renown

ThePit runs two parallel currencies, each serving a distinct purpose.

### Gold (Session Currency)
- Earned from kills, assists, bounty rewards, event rewards, and random gold pickups.
- Spent in the non-permanent items shop for consumables and temporary gear.
- Bound to a single arena session and reset only by `/thepit reset`.

### Renown (Permanent Currency)
- Earned exclusively through prestiging.
- Spent on permanent prestige perks and permanent upgrades.
- Persists across prestiges and is never reset.

Both balances are editable by admins via `/thepit gold` and `/thepit renown`.

---

## Events – Major & Minor

ThePit ships with a scheduled events system that rotates on configurable timers and announces itself in chat and on the scoreboard.

### Major Events (3)

| Event | Description | Duration |
|-------|-------------|----------|
| **Rage Pit** | All players gain Rage (damage boost) | 2 minutes |
| **Team Deathmatch** | Players split into two teams; most kills wins | 3 minutes |
| **The Beast** | One player becomes the Beast with massively boosted stats; others must kill the Beast for the reward | Configurable |

### Minor Events (5)

| Event | Description |
|-------|-------------|
| **Care Package** | A chest drops at a random location with high-tier loot |
| **Everyone Gets a Bounty** | Every online player gets a small bounty for the duration |
| **King of the Hill** | Capture a zone to earn gold over time |
| **Quick Maths** | First player to answer a math question correctly wins gold |
| **X2 Reward** | All gold and XP gains are doubled for the duration |

All events are configured in `Events.yml`, with their regions set via `/thepit setevent` during setup. Event status is fully synchronised with the scoreboard placeholder so the displayed status always reflects the current event phase (NORMAL / STARTING / RUNNING / ENDING).

---

## Bounties

Players who go on long killstreaks automatically become bounty targets. Other players can see the bounty amount above the target's head and as a particle aura when enabled. Killing a bounty target awards the bounty to the killer.

- **Auto-bounty** – triggered automatically when a player's killstreak exceeds a configurable threshold.
- **Manual bounty** – admins can set bounties on any player via `/thepit bounty <set/add/take> <player> <amount>`.
- **Bounty Hunter perk integration** – players with the Bounty Hunter perk earn bonus gold on bounty kills.
- **Event integration** – the `Everyone Gets a Bounty` minor event distributes bounties globally.
- **Bounty Aura** – configurable particle aura around bounty targets for visibility (`Bounty.Aura` in `Settings.yml`).

---

## Contracts

Contracts are repeatable objectives that reward gold and XP on completion, giving players a reason to log in every day.

- Each contract has a target (e.g., "kill 5 players with a sword", "win a King of the Hill event"), a progress counter, and a reward.
- Players can hold a limited number of active contracts simultaneously.
- The contracts pool is defined in `Contracts.yml` and is fully configurable — new contracts can be added without code changes.
- Accessed through the Contracts NPC in the arena.

---

## Non-Permanent Items Shop

A GUI accessible through the Non-Permanent Items NPC. It sells consumables and temporary gear that are lost on death or on arena leave.

| Slot | Item | Price (gold) |
|------|------|-------------|
| 11 | Diamond Sword | 150 |
| 12 | Obsidian (x8) | 40 |
| 13 | Diamond Pickaxe | 500 |
| 14 | Diamond Chestplate | 500 |
| 15 | Diamond Boots | 300 |

Golden Heads are awarded exclusively through the kill-streak reward system and are not sold in the shop.

The shop inventory is defined in `NonPermanentItems.yml` and supports custom items, prices, lore, and per-item unlock level requirements.

---

## Permanent Upgrades

Permanent upgrades are account-wide improvements bought with renown. Unlike perks, they are always active and do not occupy a perk slot. They include bonus starting gold, increased XP gain, extra perk slots, and faster respawn.

- The full list is defined in `PermanentUpgrades.yml` and is fully configurable.
- Players manage their upgrades through the `/upgrades` command or the Permanent Upgrades NPC.

---

## Trade System

Players can trade with each other using `/trade <player>`. The system is designed to prevent scams and item loss.

- **Double-confirmation** – both players must confirm the trade before it executes. Any change to either side's offer resets BOTH confirmations.
- **Anti-scam protections** – shift-clicks, number-key swaps, double-clicks, and drag-into-protected-areas are blocked inside the trade window. Permanent (kit) items cannot be offered.
- **Timeout** – the target must accept within a configurable timeout.
- **Safe cleanup** – on plugin disable, all in-progress trades are cancelled and items are returned to their owners to prevent item loss.

---

## Arena Systems

The arena is the core play space. On join, players are teleported to the spawn point, given their default loadout, and added to the arena player list.

- **Combat Tag** – players who take damage from another player are tagged for a configurable duration. Leaving the arena while tagged kills the player.
- **Killstreaks** – tracked live, broadcasted at milestones, and used to compute bounties.
- **Map Recovery** – all blocks placed by players are tracked and reverted on arena reset or server restart, including blocks broken, blocks placed, water/lava buckets, and TNT explosions.
- **Random Gold** – gold ingots spawn at configured positions on a timer, rewarding players who pick them up.
- **Spawn Protection** – players in the spawn region cannot take damage or deal damage.
- **Custom Spawn Positions** – an arbitrary number of respawn positions reduce spawn camping. The most recently set position is used first.

---

## NPCs

The plugin uses in-game NPC entities (villagers by default, configurable) at the locations set by `/thepit setnpc` to act as interactive shop and stats hubs.

| NPC | Function |
|-----|----------|
| **Stats NPC** | Opens the stats GUI |
| **Prestige NPC** | Opens the prestige GUI |
| **Permanent Upgrades NPC** | Opens the permanent upgrades GUI |
| **Non-Permanent Items NPC** | Opens the non-permanent items shop |
| **Contracts NPC** | Opens the contracts GUI |

Right-clicking any NPC opens its corresponding GUI. NPC interactions are handled by `NPCsInteract`, which listens for right-click events and routes them to the appropriate interface.

---

## Scoreboard & Tab List

### Scoreboard
- Fully configurable via `Scoreboard.yml`.
- Supports dynamic placeholders (level, gold, prestige, bounty, killstreak, online players, current event).
- Refreshes on a configurable interval.
- Uses a per-player objective to avoid flicker.
- Event status placeholder is fully synchronised with the running event state (NORMAL / STARTING / RUNNING / ENDING).

### Tab List
- Custom header and footer (configurable in `Scoreboard.yml` under `Tab.Header` and `Tab.Footer`).
- Default header: server banner block. Default footer: server address.
- Each player's tab entry shows a level prefix `[L] Name` (toggleable via `Tab.Show-Level-Prefix`).
- Tab entries are sorted by player level descending (toggleable via `Tab.Sort-By-Level`).
- When the external TAB plugin is detected, ThePit defers tab list management to TAB and becomes a no-op for tab updates.

---

## Holograms

A lightweight hologram system used for floating text displays throughout the arena.

- **Static Holograms** – for NPC labels and the unlocked features display.
- **Refreshable Holograms** – for event announcements that update in real time.
- **Version-aware** – works on both 1.8.x and newer server versions via the `VersionSupport` abstraction.
- Positions are set during setup via `/thepit setunlocked-features-hologram` and `/thepit setevent`.
- All holograms are cleaned up on plugin disable.

---

## Enderchest

Each player gets a portable, persistent enderchest accessible from configured positions in the arena.

- Contents are stored per-player in MongoDB.
- Shared across servers when cross-server sync is enabled.
- Size is configurable in `Enderchest.yml`.
- Positions are set via `/thepit setenderchest`.

---

## Chat Options

Players can customise what messages they see in chat via `/pchat` (alias `/pitchat`).

- Hide bounty broadcasts.
- Hide event announcements.
- Hide kill messages.
- Hide join/leave messages.
- Options are defined in `ChatOptionGui.yml` and are fully configurable.

---

## Custom Spawn Positions

In addition to the main spawn point, the plugin supports an arbitrary number of custom respawn positions.

- Reduces spawn camping by picking a fresh spawn location on each death.
- The most recently set custom spawn position is used first.
- `/thepit setspawn-pos <N>` – sets custom spawn position N (OP only).
- `/thepit removespawn-pos <N>` – removes custom spawn position N (OP only).

---

## Player Sync (Cross-Server)

When enabled, multiple arena servers share player progression in real time.

- **Redis pub/sub** for live updates — when a player's data changes on one server, every other server receives the update instantly.
- **MongoDB** for persistence — the authoritative data store that survives restarts and crashes.
- **Graceful degradation** — if Redis is unreachable, the plugin logs a single warning and continues in single-server mode. No data is lost.
- **Safe concurrency** – inventory and XP snapshots are written through the MongoDB document API on asynchronous tasks; inventory mutations are always applied on the main server thread.
- Enabled via `Plugin.Database.PlayerSync: true` in `Settings.yml` with Redis credentials configured.

---

## Commands & Permissions

Main command: `/thepit`

## Full Configuration

Every value is editable in the `plugins/ThePit/` directory. Nothing is hard-coded.

| File | Purpose |
|------|---------|
| `Settings.yml` | Main config: setup mode, database, Redis, bounty, diagnostics |
| `Messages.yml` | All plugin messages |
| `RankColors.yml` | Rank color definitions |
| `Prestige.yml` | Prestige tiers, renown rewards, level requirements |
| `Perk.yml` | All 28 perks (standard + prestige) |
| `PermanentUpgrades.yml` | Renown-bought permanent upgrades |
| `NonPermanentItems.yml` | Gold shop items, prices, and lore |
| `Contracts.yml` | Contract pool definitions |
| `Scoreboard.yml` | Scoreboard layout, tab header/footer, sorting |
| `ChatOptionGui.yml` | Chat toggle options |
| `Map.yml` | Arena map data |
| `Spawn.yml` | Main spawn position |
| `CustomSpawns.yml` | Custom respawn positions |
| `Enderchest.yml` | Enderchest size and positions |
| `Region.yml` | Spawn region and pit hole |
| `RandomGold.yml` | Random gold spawn positions and timers |
| `Hologram.yml` | Hologram positions and content |
| `Events.yml` | Event scheduling and configuration |
| `EventsRegion.yml` | Event region positions |
| `EventsHologram.yml` | Event hologram positions |
| `Stats.yml` | Level curve and stat tracking |

---

## PlaceholderAPI Integration

ThePit registers a comprehensive PlaceholderAPI expansion. All placeholders are prefixed with `%thepit_`.

```
%thepit_level%           # Player's current level
%thepit_prestige%        # Player's prestige level
%thepit_gold%            # Player's current gold balance
%thepit_renown%          # Player's current renown balance
%thepit_bounty%          # Player's current bounty (0 if none)
%thepit_killstreak%      # Player's current killstreak
%thepit_bestkillstreak%  # Player's best killstreak
%thepit_kills%           # Player's total kills
%thepit_deaths%          # Player's total deaths
%thepit_assists%         # Player's total assists
%thepit_kdr%             # Player's kill/death ratio
%thepit_xp%              # Player's current XP
%thepit_xp_needed%       # XP needed for the next level
%thepit_rank%            # Player's rank color name
%thepit_tag%             # Player's active tag
%thepit_prestige_tag%    # Player's prestige tier tag
%thepit_event%           # Name of the currently active event
%thepit_event_time%      # Time remaining on the current event
```

If PlaceholderAPI is not installed, the plugin still works; placeholders simply are not resolved.

---

## Database & Storage

ThePit treats data persistence as a first-class component.

- **MongoDB (Sole Backend)** – the only persistence engine. No SQLite, no flat files. MongoDB 4.4+ is required. The connection is initialised on plugin enable using credentials in `Settings.yml`. The default database name is `thePit`, with auto-created collections for players, stats, enderchests, and sync metadata.
- **Shaded Driver** – the MongoDB driver (4.11.1) is shaded into the final JAR with package relocation (`org.mongodb` → `com.nerotek01.thepit.libs.mongodb`) to avoid conflicts. The shade is configured with `minimizeJar=false` and a `ServicesResourceTransformer` to preserve the driver's `META-INF/services/` descriptors.
- **Async Everything** – player data is loaded once at join (asynchronously) and cached in-memory. All writes are flushed off the main thread. Level, prestige, gold, and renown are served from in-memory caches on the main thread; MongoDB reads happen once, and writes are always async.
- **Redis (Optional L2 Cache)** – when cross-server sync is enabled, Redis 6.x+ provides real-time pub/sub updates between servers. If Redis is unreachable, the plugin logs a single warning and continues in single-server mode. The Jedis client is shaded with relocation (`redis.clients` → `com.nerotek01.thepit.libs.redis`).
- **Graceful Shutdown** – on plugin disable, all player data is flushed, Redis subscriptions are cleaned up, and connections are closed.

---

## Diagnostics

The built-in tick monitor (`TickMonitorManager`) provides real-time performance visibility.

- Enabled via `Diagnostics.Tick-Monitor: true` in `Settings.yml`.
- Prints a console warning whenever the main thread's tick duration exceeds `Diagnostics.Tick-Threshold-Ms` (default 100 ms).
- Useful for diagnosing lag spikes and verifying that async saves, deferred hologram updates, and batched scoreboard refreshes are working correctly.
- Zero overhead when disabled.

---

## Public API

ThePit exposes a full Java API at `com.nerotek01.thepit.api.ThePitAPI` for other plugins to read and modify player data.

```java
// Access the API
ThePitAPI api = Main.getThePitAPI();

// Read and write player data
api.setGold(player, 500);
api.setPrestige(player, 3);
api.addRenown(player, 100);

// Check arena status
api.isInArena(player);
api.isCombatTagged(player);

// Read stats
api.getKills(player);
api.getKDR(player);
api.getBestKillstreak(player);
```

### Custom Events (13+)

The plugin fires detailed custom events for external plugins to listen to:

| Event | When Fired |
|-------|-----------|
| `ArenaJoinEvent` | Player joins the arena |
| `ArenaLeaveEvent` | Player leaves the arena |
| `PlayerRankupEvent` | Player reaches a level threshold |
| `PlayerPrestigeEvent` | Player prestiges |
| `PlayerStreakEvent` | Player reaches a killstreak milestone |
| `PlayerShootEvent` | Player shoots a bow |
| `PlayerArrowHitEvent` | Player's arrow hits another player |
| `PlayerGoldenHeadEatEvent` | Player eats a golden head |
| `PlayerLaunchEvent` | Player launches (e.g., via jump pad) |
| `PlayerPlaceEvent` | Player places a block in the arena |
| `GoldSpawnEvent` | Random gold spawns |
| `NonPermanentItemsBuyEvent` | Player buys from the shop |
| `SetupSetEvent` | Setup command sets a position |

---

## Frequently Asked Questions

### Pre-purchase Questions

**Q: Is this a single plugin or do I need multiple downloads?**
A: ThePit ships as a single shaded JAR containing all 28 perks, the prestige system, events, bounties, contracts, the trade system, the NPC framework, and the cross-server sync layer. Everything is included.

**Q: Does it support versions newer than 1.8.8?**
A: Currently, ThePit is exclusively engineered for 1.8.8. This single-version focus allows deep combat optimisations. If future versions are supported, they will be provided as separate, equally optimised branches.

**Q: Do I need Vault or an economy plugin?**
A: No. ThePit uses its own dual-currency economy (gold + renown). The only external dependency is PlaceholderAPI (optional but recommended). ProtocolLib, ViaVersion, and TAB are all optional.

**Q: How does the license work?**
A: One payment grants you a permanent license that covers every server you own. There are no recurring fees, no per-server charges, and no hidden costs.

**Q: Can I test the plugin before buying?**
A: Yes. Connect to `mc.hypeland.org` to experience the full plugin on a live server with no registration.

### Technical Questions

**Q: What Java version does my server need?**
A: Java 21 or newer. The JAR is compiled with `--release 21`. Spigot 1.8.8 is fully compatible with Java 21 — you only need to update your JVM.

**Q: Does ThePit work on a shared server with other plugins?**
A: Yes. ThePit manages its own arena region and does not interfere with other plugins outside the arena.

**Q: Do I need Redis?**
A: Redis is only required if you enable cross-server sync (`Plugin.Database.PlayerSync: true`). For single-server deployments, MongoDB alone is sufficient.

**Q: What happens if Redis goes down?**
A: The plugin logs a single warning and continues operating in single-server mode. No data is lost — MongoDB remains the authoritative store.

**Q: How are map changes handled?**
A: All blocks placed or broken by players are tracked in memory and automatically reverted on arena reset or server restart. No manual intervention is required.

### Support

**Q: How do I get help if something breaks?**
A: You have 24/7 direct access to the developer via Discord (`Nerotek01`) or Bale (`Nerotek`). There are no tickets, no forums, and no canned replies.

**Q: Are updates free?**
A: All updates for the current major version are included with your permanent license.

---

## Support & Purchasing

**ThePit** is a premium plugin sold exclusively by the developer.

### How to Purchase
- **Discord:** `Nerotek01`
- **Bale (Iranian users):** `Nerotek`
- **Price:** **€25.00** — one-time payment, permanent license.

### License
**Permanent, all-servers license.** Your purchase covers every server you own — from a single arena to a 50-server BungeeCord network. There are no recurring fees, no per-server add-ons, and no hidden costs.

### What You Receive
- The complete ThePit plugin JAR (shaded with MongoDB and Jedis).
- All 28 perks, fully integrated and ready to use.
- Full prestige system with renown economy.
- 8 scheduled events (3 major + 5 minor).
- Bounty, contracts, and trade systems.
- Cross-server sync layer (Redis + MongoDB).
- Public API with 13+ custom events.
- Free updates for the current major version.
- **24/7 priority support** via Discord or Bale.

### Support Promise
When an issue arises on your live network, you do not file tickets and hope for a reply. You speak directly with the developer — the person who wrote every line of code. Your uptime is our reputation.

---

<p align="center">
  <a href="https://mc.hypeland.org"><strong>Connect to the demo: mc.hypeland.org</strong></a>
</p>
