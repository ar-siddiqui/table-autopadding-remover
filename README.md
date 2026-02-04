# Table Autopadding Remover

Obsidian plugin to remove extra padding spaces that Obsidian adds to Markdown tables when files are saved.

## Motivation
Obsidian auto-pads Markdown table cells with spaces when you edit a different
row. That makes `git diff` noisy and harder to review. This plugin removes the
extra padding on save to keep diffs clean.

Background discussion: https://forum.obsidian.md/t/add-a-configurable-switch-flag-to-disable-auto-padding-of-table-cells/81531

## Features
- Normalizes table rows to single-space padding inside cells.
- Normalizes separator rows (e.g. `| ---- |` → `| --- |`) while preserving alignment colons.
- Runs automatically on save.
- Skips code fences.
- Handles `[[wikilink|alias]]` pipes without breaking cells.

## Installation

### Option 1: Manual
1. Create a folder named `table-autopadding-remover` in your vault at:
   `YOUR_VAULT/.obsidian/plugins/table-autopadding-remover`
2. Copy `main.js` and `manifest.json` into that folder.
3. In Obsidian, enable the plugin in Settings → Community plugins.

### Option 2: BRAT
1. Install the BRAT plugin.
2. Add this repo URL in BRAT.
3. Enable the plugin in Settings → Community plugins.

## Behavior
Input (on save):
```
| a    | b |
|      |   |
```
Output:
```
| a | b |
| | |
```

The plugin only rewrites table rows that start and end with `|`.

## Development
This plugin is plain JavaScript (no build step). `main.js` is the file Obsidian loads.

## Disclaimer
This plugin is purely AI generated. The author takes no responsibility for any
issues or damages resulting from its use.
