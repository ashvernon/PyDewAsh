Game Design Document: Mars Sci-Fi Overhaul
1. Vision & Concept
Transform the existing farm-sim codebase into a Mars colonization adventure, blending survival, exploration, and base-building with a touch of sci-fi wonder.

Current Base: A top-down, tile-based farming sim built with Pygame (main.py, level.py) .

New Theme: Player is a pioneering colonist on Mars tasked with terraforming regolith, managing life support, and uncovering alien mysteries.

2. Core Pillars
Survival & Resource Management

Exploration & Discovery

Base Building & Automation

Narrative & Mystery

3. Gameplay Mechanics
3.1 Movement & Interaction
Reuse: Player class handles movement, tool use, collision (player.py) player.

Overhaul: Replace farming animations with EVA suit sprites and vacuum-cleaner-style “dust” tool animations.

3.2 Tools & Equipment
Existing: Tools = hoe/axe/water; seeds = corn/tomato (player.py) player.

Mars:

Drill: Excavate regolith → yields minerals (iron, silicon).

Harvester: Collect bio-pods from biodomes.

Oxygen Dispenser: Refill O₂ tanks.

Upgrade Path: Unlock advanced tools via research.

3.3 Resource Tiles
SoilLayer handles tilling, watering, planting (soil.py) soil.

Mars:

RegolithGrid: Tracks excavation (X), hydration (W), and bio-pod planting (P).

Dust Storms: Adapt Rain/Sky classes to trigger low-visibility events and damage panels (sky.py) sky.

3.4 Base Structures
Generic sprites for decorations (sprites.py) sprites.

New Buildings:

Habitation Module: Provides shelter and seeds morale.

Greenhouse: Grows Earth plants.

Power Core: Supplies energy to machinery.

Laboratory: Unlocks research tree.

3.5 Inventory & Economy
Menu shows buy/sell (menu.py) menu.

Mars:

Supply Manifest: Inventory of metal, water, O₂ canisters.

Trade Hub: Exchange with orbiting freighters.

Dynamic Pricing: Fluctuating prices based on supply/demand.

3.6 Progression & Unlocks
Experience from tasks (mining, planting, research).

Tech Tree:

Unlock new tools and modules.

Research projects consume data resource.

4. World & Narrative
4.1 Setting
Map loaded from TMX (level.py) level. Redesign tileset to dusty reds, distant Olympus Mons silhouette, and habitat clusters.

4.2 Story Beats
Arrival: Tutorial in landing capsule.

First Outpost: Build basic structures; learn controls.

Research: Decode alien signals.

Expansion: Terraforming begins.

Revelation: Discover buried alien relics → triggers new game chapter.

4.3 Environmental Hazards
Dust Storms: Reduce visibility, slow movement, damage solar panels.

Radiation Spikes: Require players to seek shelter; drained health if outside too long.

5. Technical Mapping & Modules
Subsystem	Current Module	Mars Overhaul
Initialization	main.py	Update window title, icon, and initial loading screens.
Level Setup	level.py	Load Martian terrain TMX; place random mineral veins, alien ruins.
Player Logic	player.py	Swap tools; add O₂ management; UI for HUD (O₂ gauge, temperature).
Overlay & HUD	overlay.py	Display suit status, base power level, environmental readouts.
World Effects	sky.py, Rain	Adapt to Martian sky gradient; DustStorm class.
UI Menus	menu.py	Re-skin menu; add tabs for research, trade, mission log.
Terrain & Plants	soil.py	Rename to RegolithLayer; water → moisture generation; bio-pods.
Transitions	transition.py	Use airlock animations and pressure-wash effects during scene swaps.

6. Art & Audio Direction
Visual Style: Semi-realistic low-poly PBR look; red/orange palette; wearable UI overlays on suit.

Sprites: EVA suit idle/run/mining/watering animations.

Tilesets: Regolith, basalt rock formations, ice pockets.

Audio:

Ambient: Wind + distant creaks.

Tool sounds: Drill hum, compressor hiss (audio folder).

Music: Atmospheric sci-fi scores.

7. Roadmap


Reskin movement & tool-use.

Implement RegolithLayer with mining.



Add base structures and resource flow.

Integrate O₂/Power systems.



Implement mission log, research tree.

Create first alien relic event.



HUD enhancements.

Dust storm events & balancing.

Beta & Testing (2 weeks)

Playtest for pacing and difficulty.

Bug fixes & performance optimization.