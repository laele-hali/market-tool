# FFXIV Crafting Profit Analyzer

A Python-based Discord bot designed to help Final Fantasy XIV players on the Dynamis data center (especially Halicarnassus) monitor item prices and determine the most profitable crafting paths starting from mining.

---

## Project Purpose

This tool uses Universalis and XIVAPI to:
- Track real-time prices of ores, ingots, and crafted gear
- Calculate crafting profit margins
- Respond to user commands via Discord

---

## Data Structure

Tracked items are stored in `.txt` files inside a `data/` directory:

```
data/
├── ores.txt
├── ingots.txt
└── armour.txt
```

Each file should contain lines in the format:
```
Item Name,Item ID
```

Example:
```
Iron Ore,5166
Iron Ingot,5061
```

This allows modular item management and easy category expansion.

---

## Roadmap

### Stage 1 – Core Functionality (In Progress)

- Load item lists from `/data/*.txt`
- Fetch real-time prices from Universalis API
- Respond to commands like:
  - `!market ores`
  - `!market ingots`
  - `!market armour`

---

### Stage 2 – Profit Analysis & Sorting (Planned)

- Map ore → ingot conversions with basic recipe data
- Calculate and sort items by profit per craft
- Add command: `!market profit`

---

### Stage 3 – Smart Lookup & Discord-Based Editing (Planned)

- Command: `!market price <item>` → uses XIVAPI to find item ID and fetch price
- Command: `!market add <category> "<item name>"` → resolves name to ID and adds to the list
- Validate name format and prevent duplicates
- Confirm additions before saving

---

## Example Commands

```
!market ores
!market ingots
!market profit
!market price silver ore
!market add ores "Titanium Ore"
```

---

## Technologies Used

- Python 3
- [discord.py](https://discordpy.readthedocs.io/)
- [Universalis API](https://universalis.app/docs/index.html)
- [XIVAPI](https://xivapi.com/docs)

---

## Future Ideas

- Scheduled daily summaries of best crafts
- SQLite support to replace flat files
- Web dashboard with charts
- Inventory-based profit simulation

---

## License

MIT License
