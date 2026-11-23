# ✎ NOTE//PAD — checklist notes with deadlines

![macOS](https://img.shields.io/badge/macOS-Übersicht-3ef0ff?style=flat-square&logo=apple&logoColor=white&labelColor=040914) ![Vibecoded](https://img.shields.io/badge/vibecoded-with%20Claude-ff5ad9?style=flat-square&labelColor=040914)

Quick notes that clean up after themselves. Type a note, tick it off when it's done, and anything you forget expires into a bin you can restore from.

| File | What |
|:--|:--|
| `notepad.jsx` | The widget (230 × 314, left of the wallet by default) |
| `notepad.py` | Backend: notes, deadlines, expiry, bin |

## Use it

- **Add:** click the bottom field, type, ⏎. Esc leaves the field.
- **Tick:** tap a row. It's struck through and a bar drains for 5 s (tap again to undo), then it folds into the bin.
- **Expire:** notes move to the bin 3 days after you wrote them. The bin deletes them for good after 3 years.
- **Bin:** `BIN ▸` (top right) lists ticked ✓ and expired ⌛ notes, newest first. `↺` (tap twice) puts one back with a fresh 3 days.

## Deadlines

Put **one** token anywhere in the note. Digits only; fewer digits = less specific:

| Token | Meaning | Examples |
|:--|:--|:--|
| `t/DDHHMM` | countdown from now | `t/45` = 45 days · `t/0012` = 12 h · `t/000030` = 30 min |
| `d/DDMMYY(HHMM)` | a date | `d/05` = next 5th · `d/0511` = next 5 Nov · `d/0511261430` = 5 Nov 2026 14:30 |

A date with no time means 23:59. The row shows `⏱` time left: cyan, then amber under 24 h, then red `LATE`. Deadline notes expire 3 days *after* the deadline. A bad token (31 Feb, a past date) keeps your text in the field and flashes the reason.

## Data

`~/Library/Application Support/STUDYTERM/standalone/data/notepad.json` (override with `NOTEPAD_DATA`). In my own setup the same backend points at a file in my Obsidian vault so it syncs through iCloud. Set `NOTEPAD_DATA` to do the same with any synced folder.

## 🚀 Install

1. Download this repo (green **Code** button → *Download ZIP*) and double-click **`install.command`**. The first time, macOS may block it: right-click → *Open*.
   It installs [Übersicht](https://tracesof.net/uebersicht/) if you don't have it and copies `notepad.jsx` into its widgets folder, plus `notepad.py` into `~/Library/Application Support/STUDYTERM/standalone/bin/`.
2. Click the widget to use it. If clicks fall through to the desktop: Übersicht menu-bar icon → this widget → turn on interaction.

- **Needs:** macOS 13+ · `python3` 3.8+ (run `xcode-select --install` if you don't have it)
- **By hand:** Copy `notepad.jsx` into Übersicht's widgets folder (menu-bar icon → *Open Widgets Folder*) and `notepad.py` into `~/Library/Application Support/STUDYTERM/standalone/bin/`.
- **Remove:** delete `notepad.jsx` from the widgets folder. Your data in `~/Library/Application Support/STUDYTERM/standalone/data/` stays.

## 🎨 Look and position

Out of the box it sits in its default spot in the cyan terminal theme. Install [**WIDGET//CTL**](https://github.com/SlicingReaper/widgetctl) to drag it anywhere on a grid and pick from 16 colour schemes × 8 styles, and to get `⌃⌥⌘W`, which hides all widgets at once.

## 🧩 Part of a collection

This widget is one of twelve that share the same retro-terminal look, the same theming and the same show/hide hotkey. Each works on its own; together they make a desktop dashboard.

| | Widget | What |
|:-:|:--|:--|
| 💰 | [**WALLET//Ð**](https://github.com/SlicingReaper/points-wallet-widget) | Points wallet: earn for habits, spend on rewards, lock savings, keep a streak |
| 🔥 | [**75//HARD**](https://github.com/SlicingReaper/75-hard-widget) | 75 Hard challenge tracker: 7 daily tasks, day counter, auto-fail on a missed day |
| ⏱️ | [**STUDY//TERM**](https://github.com/SlicingReaper/study-timer-widget) | Study stopwatch that logs what you did, with a stats page and points |
| ✎ | [**NOTE//PAD**](https://github.com/SlicingReaper/notepad-widget) ← you are here | Checklist notes with deadline countdowns, auto-expiry and a bin |
| “ | [**QUOTE//DAY**](https://github.com/SlicingReaper/quote-of-the-day-widget) | A new quote every midnight from a pool of 300, with likes and your own quotes |
| ▦ | [**TETRIS//GRID**](https://github.com/SlicingReaper/tetris-widget) | Tetris on the desktop: hold, ghost piece, levels, best score |
| ◉ | [**PONG//SOLO**](https://github.com/SlicingReaper/pong-widget) | Single-player Pong: keep the ball up, it speeds up every hit |
| ◎ | [**PONG//DUO**](https://github.com/SlicingReaper/pong-duo-widget) | Two-player Pong, 3 widgets wide: W/S vs ↑/↓, first to 7 |
| ⊞ | [**2048//TILE**](https://github.com/SlicingReaper/2048-widget) | 2048 with undo, keyboard or drag, saved between sessions |
| ⌂ | [**OUTPOST//**](https://github.com/SlicingReaper/outpost-colony-widget) | Colony-trading game: claim land, outfit robots, trade against 3 AI rivals |
| ☠ | [**DOOM//TERM**](https://github.com/SlicingReaper/doom-widget) | DOOM shareware Episode 1 in a 2-column widget: WebAssembly engine, savegames kept |
| 🎛️ | [**WIDGET//CTL**](https://github.com/SlicingReaper/widgetctl) | Menu-bar app that arranges and themes all the widgets, plus a ⌃⌥⌘W show/hide hotkey |

**Install all of them at once:** [`vibecoded` → install-all.command](https://github.com/SlicingReaper/vibecoded) · 🤖 Vibecoded with [Claude](https://claude.ai): I designed, directed and tested it, the AI wrote most of the code.
