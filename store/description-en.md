# Yahtzee Dice — Store Submission Materials

## Short description (CrazyGames / GameDistribution / itch.io)

The classic five-dice scorecard game. Roll up to 3 times a turn, hold your
dice, chase straights, full houses and the big 50-point YAHTZEE. Full 13-row
scorecard, +35 upper bonus, joker +100 rule, 3D tumbling dice. (≤200 chars body below)

Roll 5 dice, hold the keepers, score all 13 rows. Chase straights, full houses
and the big 50-point Yahtzee — with a +100 joker bonus. Free, no install.

## Details

- Genre: Dice / Board / Casual (classic Yahtzee-style)
- Controls: Mouse / Touch (tap dice to hold, tap scorecard rows to score).
  Keyboard: R or Space to roll, 1–5 to hold dice, Enter to restart.
- Rules implemented: Ones–Sixes upper section with +35 bonus at 63+;
  Three/Four of a Kind (all-dice sum); Full House 25 (five-of-a-kind also
  counts as a Full House); Small Straight 30 (any 4 consecutive dice,
  order ignored); Large Straight 40 (5 consecutive); Yahtzee 50; Chance (sum).
- Simplified Joker rule (stated in-game under RULES): after the Yahtzee row is
  filled, each later five-of-a-kind awards a +100 bonus and may be written as
  50 into any empty row.
- Exactly one empty row must be scored per turn; rows cannot repeat. Game ends
  after 13 rounds with a full scorecard recap. Best score saved locally
  (localStorage, try/catch guarded).
- Features: 3D tumbling dice (0.8s roll, canvas-rendered with perspective),
  dice-clatter sound effects, top-3 scoring suggestion highlights, mute toggle
  with persisted preference, single-file HTML5 (no external assets), works
  offline once loaded.
- Tech: Vanilla JavaScript, Canvas, WebAudio. No frameworks, no tracking,
  no external links in gameplay.

## Tags

dice, yahtzee, board, classic, casual, scorecard, single-file, puzzle

## CrazyGames submission checklist
- [x] Self-contained index.html (SDK loads only on crazygames domains)
- [x] gameplayStart / gameplayStop / happytime events wired; loadingStart / loadingStop on CrazyGames
- [x] Responsive (portrait-first, scales to viewport, touch + mouse + keyboard)
- [x] No external links inside gameplay, no analytics
- [ ] Cover: cover-16x9.png (1280×720)
- [ ] Screenshots: screenshot-raw.png (1280×800)

## GameDistribution
- Upload `yahtzee-dice-gd.zip` (contains only index.html at zip root).

## itch.io
- Upload zip `yahtzee-dice-itch.zip` (contains only index.html), mark
  "This file is playable in browser", entry file: index.html,
  viewport 480×620 (portrait), kind: html.
- Pricing: $0 (donations optional)
