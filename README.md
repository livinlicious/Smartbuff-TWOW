# SmartBuff for Turtle WoW

[![Game Version](https://img.shields.io/badge/wow-1.12.1-blue.svg)](https://github.com/Azzc0/SmartBuff)
[![Turtle WoW](https://img.shields.io/badge/TurtleWoW-1.18-green.svg)](https://turtle-wow.org/)

SmartBuff addon optimized for Turtle WoW 1.18. Automatically buffs yourself, party members, raid members, and pets with a single keybind.

## What's New in This Version

This fork includes critical fixes and optimizations for Turtle WoW 1.18:

### Turtle WoW Compatibility Fixes
- **Fixed negative item counts**: Turtle WoW's `GetContainerItemInfo` API returns negative stack counts, which broke reagent detection. Now handles both negative and positive values correctly.
- **Fixed weapon buff initialization**: Weapon buffs (oils, stones, poisons) are now properly loaded on game startup, not just after `/reload`.
- **Fixed bag loading timing**: Weapon buffs no longer disappear after a full game restart due to bags loading after addon initialization.

### Weapon Buff Improvements
- **Priority-based buffing**: Weapon buffs now apply LAST in the buff sequence, preventing GCD conflicts with other buffs.
- **Smart buff order**: Regular buffs (Mark of the Wild, Thorns, etc.) are applied first, then weapon enchants are applied when nothing else needs casting.
- **Shapeshift support**: Weapon buffs now work correctly in Tree of Life form while remaining blocked in Cat/Bear forms (as intended).
- **Clean menu display**: Only weapon buffs for items actually in your bags are shown in the settings menu, preventing clutter.

### Technical Improvements
- **MH (Main Hand) checkbox**: Now defaults to enabled for weapon buffs, fixing first-time setup issues.
- **Saved variables migration**: Existing weapon buff settings are automatically fixed if they have incorrect default values.
- **Icon handling**: Missing items use placeholder icons instead of breaking the buff list.

## Installation

1. Download this repository
2. Extract the `SmartBuff` folder to your `World of Warcraft/Interface/AddOns/` directory
3. Restart the game or reload UI with `/reload`

## Usage

### Basic Commands
- `/sb` or `/smartbuff` - Cast buffs on yourself/party/raid
- `/sbm` - Open options menu
- `/sb toggle` - Enable/disable SmartBuff
- `/sb menu` - Show/hide options menu

### Keybinding
Bind a key in the game's keybinding menu under "SmartBuff" for quick access.

### Minimap Button
- **Left click**: Open options menu
- **Right click**: Enable/disable SmartBuff

## Features

- **All classes supported**: Druid, Mage, Priest, Warlock, Hunter, Shaman, Warrior, Rogue, Paladin
- **Smart buff detection**: Checks what buffs are needed before casting
- **Template system**: Configure different buff sets for Solo, Party, Raid, Battleground, etc.
- **Group buffs**: Supports Gift of the Wild, Arcane Brilliance, Prayer of Fortitude, Prayer of Spirit
- **Class buffs**: All Paladin Greater Blessings
- **Weapon buffs**: Shaman enchants, Rogue poisons, oils, stones, whetstones (with reagent checking)
- **Pet support**: Buffs hunter and warlock pets
- **Rebuff timer**: Set custom timers for when to reapply expiring buffs
- **Buff reminder**: Visual/audio notifications for missing buffs
- **Level-based buffs**: Automatically uses appropriate rank based on target level
- **Tracking abilities**: Supports tracking spells (Find Herbs, Track Humanoids, etc.)

## Configuration

Open the menu with `/sbm` and configure:
- Which buffs to use in each template
- Enable/disable buffs for self, party, or raid
- Set rebuff timers for each buff
- Configure main hand/off hand weapon enchants
- Enable/disable combat casting
- Set up auto-buff on login/rest

## Credits

- **Original Author**: Aeldra (EU-Proudmoore)
- **Turtle WoW Port**: Lexiebean
- **TWOW 1.18 Fixes**: This fork

## Original Repository

Based on [SmartBuff by Azzc0](https://github.com/Azzc0/SmartBuff)

## License

Original addon license applies.
