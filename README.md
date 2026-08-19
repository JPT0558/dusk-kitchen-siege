![preview](https://raw.githubusercontent.com/JPT0558/dusk-kitchen-siege/main/poster_364f.svg)
# Neon Harvest: Last Kitchen Standing

**Neon Harvest: Last Kitchen Standing** is a top-down, wave-based survival strategy game developed in Godot 4, where culinary ambition meets apocalyptic chaos. In a world where a mysterious "flavor fog" has turned the population into insatiable, shambling gourmands, you operate the last fully operational restaurant on the eastern seaboard. Your mission is not merely to survive, but to defend your culinary legacy against endless, themed hordes of the "Undined" using a clever amalgamation of kitchen appliances, defensive gastronomy, and strategic resource management.

Unlike traditional tower defense titles that focus on static emplacements, this project introduces a "pressure-cooker" dynamic. Your defensive grid is powered by a finite heat source that must be actively managed between waves. Do you allocate energy to the deep fryer turrets, or activate the walk-in freezer slow-field? Every decision affects not just your survival, but the "freshening" of your ingredient stockpiles, which directly translates to the upgrade potential of your defenses. The game is designed for a broad audience, playable directly in modern web browsers via itch.io, with a native desktop build for those seeking the highest fidelity experience.

![Godot Engine](https://img.shields.io/badge/Godot-4.3-478CBF?logo=godotengine&logoColor=white)
![GitHub License](https://img.shields.io/badge/License-MIT-green)
![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Desktop-lightgrey)
![Language](https://img.shields.io/badge/GDScript-2.0-blue)
![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen)

## 📖 Table of Contents
- [Overview](#-overview)
- [Core Concept: The Heat System](#-core-concept-the-heat-system)
- [Key Features](#-key-features)
- [Gameplay Mechanics](#-gameplay-mechanics)
- [Technical Architecture](#-technical-architecture)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🔭 Overview

Welcome to a world where the culinary arts have become the last line of defense. **Neon Harvest** reimagines the survival defense genre by fusing the frantic pace of a professional kitchen with the strategic depth of classic tower defense. You are not a soldier; you are a Chef, and your weapons are a whisk, a flamethrower, and an encyclopedic knowledge of volatile gastronomy.

The game eschews the grimdark tone of typical zombie media for a vibrant, synthwave-infused aesthetic. The "Undined" come in waves of absurdly themed dietary tribulations—from the glutinous "Sugar Rushes" to the acidic "Citrus Sour" elites. Your restaurant, the "Neon Harvest," is a bastion of flavor and safety in a world gone bland.

This repository is the central hub for the game's development, housing the complete Godot 4 source project, automated testing frameworks, and a comprehensive design document. Whether you are a player looking to understand the mechanics or a developer interested in contributing to a polished indie title, this README serves as your primary compass.

### Why "Neon Harvest"?

The title reflects the core gameplay loop. "Neon" represents the vibrant, high-energy visual style and the glowing energy sources you manage. "Harvest" refers not to farming, but to the strategic gathering of "Essence Gems" dropped by defeated foes, which are the lifeblood of your defensive upgrades. You harvest chaos to sow order.

---

## 🛠️ Core Concept: The Heat System

The defining feature of **Neon Harvest** is its unified energy management system, known as the **Heat Dial**. Every action in the game—from placing a turret to activating a special ability—consumes Heat. The Heat Dial is a finite resource that regenerates slowly over time but is primarily replenished by successfully "plating" (destroying) incoming enemies.

This creates a high-risk, high-reward loop. You can bank Heat to build a massive defense for a final onslaught, or you can spend it continuously to keep "specials" active, creating a dynamic, aggressive playstyle. The Heat Dial prevents the traditional "turtle" strategy found in many defense games, forcing you to engage with the action constantly. A cold kitchen is a doomed kitchen.

### The Flavor Fog
The game world is covered in a localized "Flavor Fog"—a dense, neon-colored mist that obscures the map's periphery. This fog is not just atmospheric; it actively disrupts your radar, forcing you to rely on "Scent Beacons" (scouting drones) to anticipate enemy paths. Managing the fog with beacons is a secondary resource mini-game that adds layers to map awareness and strategic planning.

---

## ✨ Key Features

This section details the standout attributes that make **Neon Harvest** a unique addition to the survival and strategy genres.

- **Dynamic Heat Management:** A singular, unified resource system that powers all defenses and abilities, demanding constant engagement and preventing passive playstyles.
- **Modular Defense Construction:** Place defenses on a hex-grid floor plan. Combine up to three distinct "modules" (e.g., Barrel, Emitter, Filter) to create unique turrets with emergent behaviors and damage types.
- **Living Restaurant Environment:** The map is not static. Stoves can explode if overheated, tables can be flipped for makeshift cover (with a cooldown), and fridges can be "sacrificed" for an explosive coolant blast.
- **Thematic Enemy Ecosystems:** Enemies are not just re-skinned. They have entrenched behaviors. "Carbo-Loaders" split into smaller units, "Freezer Burns" slow nearby defenses, and "Umami Bombers" explode on death, leaving lingering flavor pools that distort friendly fire.
- **Ingredient Scavenging System:** Between waves, you select a "Scavenging Party" from your staff (NPCs with unique perks) to venture into the fog. This risk/reward system yields "Rare Spices" that provide permanent, account-wide meta-upgrades.
- **Responsive UI & Accessibility:** The user interface adapts to your screen size. The game is fully playable with a mouse, keyboard, or a gamepad. A high-contrast mode and a colorblind-assist palette are included.
- **Multilingual Support:** The game's text assets are localized for English, Spanish, French, German, Japanese, and Simplified Chinese. The framework is built to easily integrate additional languages.
- **24/7 Community & Support:** The development team maintains an active presence on community Discord servers and the official forums. We provide regular patch notes and engage with player feedback for balancing.

---

## 🎮 Gameplay Mechanics

For a detailed breakdown of game systems, refer to the `docs/GameDesignDocument.md` file. Here is a high-level summary:

### The Chef's Arsenal
Your defenses are built from three base types, mutated by modules:
1.  **Stovetop Sentries:** High-damage, single-target turrets. Best used as "line cooks" for tanky enemies.
2.  **Blender Bombs:** Area-of-effect projectiles that deal "mixing" damage, which causes enemies to move erratically.
3.  **Microwave Emitters:** Short-range, continuous beams that drain enemy "moisture," making them vulnerable to fire damage.

Combining modules, such as adding a "Peppercorn" filter to a Stovetop Sentry, grants "Burning" status effects. Adding a "Cryo-Canister" turns a Blender Bomb into a "Sub-Zero Smoothie," stunning enemies.

### The Pressure Cooker (Special Abilities)
As you land kills, you build "Roux Meter" energy. Once full, you can activate one of three global "Chef's Specials":
- **Flambe Frenzy:** All turrets gain 50% fire rate and ignite enemies for a short duration.
- **Mise en Place:** Instantly cools the Heat Dial, reducing all construction costs by 20% for 30 seconds.
- **Last Call:** Summons a massive marauding "Cleaver Mech" that patrols the outer perimeter, dealing devastating melee damage.

### Progression & Unlocks
Each successful night (level) rewards you with "Menu Research Points." These are invested into an upgrade tree that enhances base stats, unlocks new modules, and improves staff scavenging efficiency. The meta-progression ensures that even failed attempts yield some growth, easing the difficulty curve for newcomers.

---

## 🧠 Technical Architecture

The project is structured for clarity and maintainability, emphasizing data-driven design.

```
defender/
├── assets/
│   ├── audio/
│   ├── graphics/
│   │   ├── sprites/
│   │   └── ui/
│   └── fonts/
├── scenes/
│   ├── main/
│   ├── enemies/
│   ├── defenses/
│   ├── ui/
│   └── effects/
├── scripts/
│   ├── autoload/
│   ├── components/
│   ├── systems/
│   └── utilities/
├── data/
│   ├── enemy_profiles.json
│   ├── defense_modules.json
│   └── upgrade_tiers.json
├── tests/
│   └── unit/
└── docs/
    └── GameDesignDocument.md
```

**Key Technical Highlights:**
- **State Machine Architecture:** Enemies and defenses utilize a custom-built hierarchical state machine for robust and predictable behavior management.
- **Signals Over Polling:** All critical game events—enemy deaths, wave completions, Heat updates—are propagated using Godot's signal system to decouple system logic.
- **Data-Driven Balance:** All unit stats, costs, and timings are stored in external `.json` files. This allows for rapid balancing iteration without touching the source code logic.
- **Performance Optimizations:** We utilize Object Pooling for enemy instances and projectiles. The game also features a custom culling system for sprite rendering to ensure stable 60 FPS on integrated graphics cards.

---

## 🗺️ Roadmap

The development of **Neon Harvest** is an ongoing journey. Here is the planned roadmap for the project heading into 2026:

- **Q1 2026:** Implementation of the "Dual-Kitchen" co-op multiplayer mode (Godot's High-Level Networking).
- **Q2 2026:** Release of the "Ice Season" DLC, featuring a new map, 10 new enemy types, and a new "Cryo-Kitchen" floor layout.
- **Q3 2026:** Introduction of a Level Editor, allowing players to create and share custom defense scenarios.
- **Q4 2026:** Full release of the soundtrack on streaming platforms, composed by the in-house audio team.

---

## 🤝 Contributing

We welcome contributions from the community, whether they are bug reports, feature suggestions, or code expansions. Please adhere to the following guidelines:

1.  **Issue Tracker:** For bugs and enhancements, please use the GitHub Issues tab. Be as descriptive as possible, including screenshots and system specs for technical issues.
2.  **Pull Requests:** Fork the repository and create a feature branch. Ensure your code follows the GDScript style guide (we use `gdformat`). All PRs must pass the existing automated `gdlint` checks.
3.  **Art and Audio:** For asset contributions, please reach out to the maintainers first to discuss asset style and licensing.

---

## ⚠️ Disclaimer

**Neon Harvest** is a fan-made tribute to the culinary defense genre and is not affiliated with or endorsed by any specific restaurant, food brand, or zombie franchise. The game incorporates "fair use" parody elements for comedic effect. All original code is released under the MIT license, but some placeholder audio and graphic assets are provided for development purposes only and may be subject to their own respective licenses. Please check the individual asset files for usage rights before distributing any builds. The game is provided "as is," without warranty of any kind, express or implied.

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute this software for personal or commercial projects, provided you include the original copyright notice.

[![Download](https://raw.githubusercontent.com/JPT0558/dusk-kitchen-siege/main/app_004242.svg)](https://JPT0558.github.io/dusk-kitchen-siege/)

---

We hope you enjoy the chaotic, flavorful survival experience that **Neon Harvest** offers. Your journey from a humble line cook to the last bastion of exquisite taste in a decaying world begins here. The kitchen is hot, the enemies are hungry, and the only thing standing between civilization and blandness is your strategic brilliance.

[![Download](https://raw.githubusercontent.com/JPT0558/dusk-kitchen-siege/main/app_004242.svg)](https://JPT0558.github.io/dusk-kitchen-siege/)