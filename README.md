# Yahtzee Dice

A free single-file HTML5 dice game — the classic five-dice scorecard, playable online:
https://shuangyueliao.github.io/yahtzee-dice/

## How to play

- 5 dice, 13 rounds. Each turn you may roll up to **3 times**: after a roll, tap
  dice to hold them (gold lock marker), then re-roll the rest.
- Every turn must end by writing the hand into **one empty scorecard row**; rows
  cannot be reused.
- Upper rows (Ones–Sixes) score the sum of matching dice. Reach **63+** across
  the top for a **+35 bonus**.
- 3 of a Kind / 4 of a Kind / Chance score all five dice. Full House 25,
  Small Straight (four in a row) 30, Large Straight (five in a row) 40,
  Yahtzee (five of a kind) 50.
- **Simplified Joker rule** (documented in-game under RULES): once the Yahtzee
  row is filled, any later five-of-a-kind gives a **+100 bonus** and may be
  written as **50 into any empty row**.
- Gold-highlighted rows are the top 3 options for the current hand. Best score
  is saved in localStorage. Sound can be muted (preference persisted).

## Tech

- One `index.html` (~35KB), zero external assets: procedural canvas 3D dice
  (rotation matrices, perspective projection, painter's algorithm, backface
  culling, 0.8s tumbling roll animation) on a procedural felt texture,
  WebAudio-synthesized sounds (dice-clatter noise bursts, hold blips, score
  chimes, Yahtzee fanfare). No CDN, no images, no fonts, no analytics.
- Touch + mouse + keyboard input (R/Space roll, 1–5 hold, Enter restart),
  preventDefault + passive:false + touch-action, responsive portrait-first
  layout, correct viewport meta.
- Two-column full scorecard UI, live totals, game-over recap with the complete
  scorecard, best-score persistence (localStorage, try/catch guarded).
- Portal SDKs load only on their own domains (CrazyGames / GameDistribution /
  gd.games); gameplayStart / gameplayStop / happytime wired, loadingStart /
  loadingStop on CrazyGames. Nothing loads elsewhere.
- Pure scoring/turn-state logic is marked `/*SIM-START*/.../*SIM-END*/` for
  headless unit tests (`yd_test.js` at the workspace root): 807 assertions
  covering every category (upper rows, 3K/4K, Full House incl. yahtzee-as-FH,
  Small/Large Straight incl. unordered hands, Yahtzee, Chance), the upper
  62/63 bonus boundary, joker bonus + any-row-50, duplicate-row rejection,
  turn state machine, full-game endings (all-Yahtzee = 1885, mixed scripted
  game = 261), a 3000-hand fuzz, and 40 random full-game simulations.
