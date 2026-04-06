# Duke Village Platformer

Single-file 2D village action-adventure built with HTML, CSS, and JavaScript.

Main game file: duke_village_platformer.html

## Overview

You play as a priest exploring Agios Blueberry Village. The game blends:

- Exploration across a large overworld and many interiors
- Quest progression and NPC dialogue
- Fruit collection and village economy
- Blessing/miracle abilities (chicken, rain, wind)
- Day/night cycle with night-only content
- Boss combat with day/night enemy swap
- Java MCQ challenge content

The game is designed to feel like a compact, story-driven RPG with arcade combat and interactive village systems.

## Core Gameplay Loop

1. Explore the village and enter buildings.
2. Talk to villagers to collect gossip and coins.
3. Gather fruit (blueberries, bananas, apples).
4. Accept and complete quests for rewards.
5. Spend coins on cafe items or miracles.
6. Use blessings strategically in the overworld.
7. Fight the overworld boss (day: Endermar, night: Nether).
8. Complete all fruit + all quests to trigger the final completion banner.

## Controls

### Keyboard

- Move: Arrow keys or W A S D
- Interact/Action: Space, Enter, Z, X
- Miracle Chicken: C
- Miracle Rain: R
- Miracle Wind: V

### Mouse / Touch

- Tap/click villagers, doors, signs, and interactables
- On-screen joystick for movement (mobile-friendly)
- Attack button appears when boss combat is relevant
- HUD panels are collapsible/toggleable

### UI Buttons

- Fullscreen
- Restart
- Zoom in/out
- Miracle buttons (Chicken, Rain, Wind)

## Progression and Win Condition

The game is considered fully complete when both are true:

- All fruit is collected
- All quests are turned in

When complete, a village completion banner appears with final fruit and coin stats.

## Quests

Current quest set includes:

1. Blueberry Basket

- Giver: Yiayia
- Goal: Bring 5 blueberries

2. Village Donations

- Giver: Mayor
- Goal: Collect 18 coins for village fund

3. Power Up the Tech Hub

- Giver: Tech Steward (Deacon)
- Goal: Activate server core in tech hub

4. Fruit for the Shop

- Giver: Merchant Eleni
- Goal: Bring 2 bananas and 2 apples

5. Collect All Gossip

- Goal: Hear every village rumor
- Reward includes wind blessing charges

6. Cafe Starter

- Goal: Buy 1 coffee and 1 sweets

7. Athina's Chicken Stove

- Giver: Athina
- Goal: Bring 1 chicken
- Result: Spawns a decorative stove and custom dialogue

8. Moonlight Swim (night-only)

- Giver: Takis
- Goal: Enter northern pool at night

9. Grand Tichu Witness (night-only)

- Giver: Yorgos (Tichu table)
- Goal: Speak with Christos at night and report back

10. Java Drill: Tech Hub

- Goal: Master all 15 Java MCQs in tech hub

11. Java Drill: School

- Goal: Master all 15 Java MCQs in school

## Economy and Items

### Currencies and Resources

- Coins
- Fruit inventory
- Coffee
- Sweets
- Wind blessing charges

### Shops

- West Coffee barista sells coffee (5 coins)
- East Coffee barista sells sweets (7 coins)

### Night shop rule

At night, only West Coffee and East Coffee are open. Other building entries are blocked with a notice.

## Day/Night System

- Time advances continuously using timeOfDay and dayNightSpeed
- Overworld visual tint changes with time
- Night enables special dialogue and night-only quests
- Transitioning day <-> night resets active enemy fight state

Night gameplay includes:

- Night-only quests
- Night-specific villager lines
- Overworld enemy swap to Nether

## Combat and Enemies

### Player combat

- Action/attack uses a directional hitbox
- Cooldown and brief attack animation
- Player HP and invulnerability window after damage

### Overworld enemy swap

- Day enemy: Endermar
- Night enemy: Nether
- Both share the same arena/spawn region near the tech hub

### Enemy behavior

- Contact damage
- Projectile/orb attacks
- Arena pressure and retreat behavior
- Reward coins on defeat

Battle HUD updates dynamically with active enemy name and HP.

## Miracles and Weather

### Chicken Blessing

- Cost: 100 coins
- Spawns wandering chickens

### Rain Blessing

- Cost: 200 coins
- Starts timed rain effect

### Wind Blessing

- Uses wind charges
- Charges unlocked via gossip quest completion
- Triggers timed wind effect

Miracles are restricted to the overworld and blocked during transitions/chanting conflicts.

## Swimming and Water

- Player can enter pool/water zones
- Movement slows while in water
- Swim-like visual treatment applied
- Night pool interaction contributes to Moonlight Swim quest progress

## World Content

The game includes a broad set of locations and social spaces, including:

- Overworld village with paths, trees, fences, ponds, decor
- Tech hub interior
- School interior and schoolyard content
- Fruit market interior
- Multiple houses
- West Coffee and East Coffee interiors
- Tichu table scene near coffee area

Many villagers have unique outfits, movement behavior, gossip text, and optional night dialogue.

## Java MCQ Mode

- Integrated modal challenge system
- Progress UI and per-question feedback
- Includes explanation flow and retry/next interactions
- Two separate quest tracks (tech hub and school)

## Technical Architecture

Project style:

- Single-file implementation in duke_village_platformer.html
- No external framework required
- Canvas rendering with UI overlay and game-state-driven updates

Main architecture elements:

- State object holding maps, entities, inventory, quests, timers, weather, boss state
- Update loop handling movement, collisions, dialogue, combat, particles, transitions
- Render pipeline for map, entities, overlays, HUD, weather/day-night effects
- Data-driven quest and NPC definitions

## How To Run

Option 1:

1. Open duke_village_platformer.html directly in a browser.

Option 2:

1. Serve folder with a simple local static server.
2. Open the served URL in your browser.

No build step or package install is required.

## Tuning Guide

Useful values to tweak in code:

- dayNightSpeed: day/night pacing
- Player speed and water slowdown multiplier
- Miracle costs and weather durations
- Enemy HP/reward/projectile cadence
- Quest rewards and requirements
- Overlay intensities for night visuals

## Future Feature Ideas

Possible additions if you want to expand the game later:

- Multiplayer with chat for shared village exploration and co-op quests
- Expanded combat encounters with new enemy types, combo attacks, and party support
- Save/load support so progress persists between sessions
- Crafting or cooking systems that use fruit and shop items
- More village events, festivals, and time-limited side quests
