# Huedrop

**Drop blocks, clear lines. Fill a line with one colour for a pure clear.**

A block-placement puzzle for the browser with a colour twist. Drag shapes onto an 8x8 board and fill complete rows or columns to clear them.

## How to play

- **Drag a block** from the tray onto the board. Place all three to get a new set.
- **Fill a row or column** to clear it. Clearing several lines at once pays much more.
- **Pure clears.** A line made of a single colour pays double, so plan your colours. Each colour also has its own shape mark.
- **Keep the combo alive.** Every clear raises the multiplier. You have two moves without a clear before it resets.
- **The game ends** when none of your blocks fit. Blocks that no longer fit turn grey.

## Features

- 37 block shapes, with scoring that rewards multi-line clears, pure lines, combos and a perfect clear (an empty board).
- **Fair hands.** The game never deals a hand that cannot be placed at all, and it eases off when you are in trouble.
- **Daily game** with a shared daily seed, plus a saved best score and stats.
- **Touch friendly.** Blocks are lifted above your finger while you drag so you can see where they land.
- Light and dark themes, sound and vibration that can be switched off.

## How it works

- `engine.js` is the pure logic: shapes, scoring and the hand picker, with a seeded random number generator.
- `sweep.js` and `test.js` simulate thousands of games with random, sloppy and greedy bots to tune how forgiving the game is.

## Play

Open `huedrop.html` in any browser, on a phone or desktop. It is a single file with no server, no accounts and no install. Fonts load from Google Fonts when online and fall back to system fonts offline. Progress is saved in your browser (`localStorage`).

You can also host it on any static site (GitHub Pages, Netlify, itch.io): upload the file and open it.

## Develop

Rebuild the single playable file from source:

```
node build.js
```

Run the logic tests (Node 18 or newer):

```
node test.js
```

## Project layout

```
engine.js    game rules and logic (no DOM)
ui.js        rendering, input and sound
style.css    layout and light and dark themes
body.html    page markup
build.js     bundles everything into one playable .html
test.js      logic tests
```

Extra file in this game: `sweep.js` (balance simulations, run with `node sweep.js`).

## Limitations

- Built and tested with an automated browser (headless Chromium with touch events) and simulated play. It has not been playtested on many real phones, so difficulty and feel may need tuning.
- Block puzzles are a crowded genre. The colour rule and combos are the twist, but expect comparisons to similar games.
- Sounds are generated in the browser and are simple.

## License

Add a `LICENSE` file before publishing (MIT is a common choice for small games).
