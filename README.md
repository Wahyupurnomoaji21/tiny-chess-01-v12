[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Wahyupurnomoaji21/tiny-chess-01-v12/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Wahyupurnomoaji21/tiny-chess-01-v12/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

[Tiny Chess 01 bounty on make.fun](https://make.fun/bounty/tiny-chess-01)

# Tiny Chess Engine v12

From-scratch 0x88 engine, packed to 3,614 bytes (Python stdlib only):
PVS + transposition table + null-move pruning + LMR + quiescence +
check extension; material + piece-square eval with pawn-shield king
safety and tapered king value; eval-conditional root repetition
filter. Fixed 90,000-node budget per move (deterministic, no clock).

## v12 recipe

Eval v4 + search v11, plus a killer-move table (KM[128]), a
90,000/80,000 move-ordering bonus, and killer updates on beta cutoff.

## Practice trials (kit-v3, 6 games each, 90k nodes)

Independent verification runs (coordinator, not the builder):

- Trial 0: Elo **1654** (5W/0D/1L, spare_plies 513) — wins vs
  depth-2, depth-3, depth-4, nodes-100k, nodes-250k; loss vs
  nodes-500k. Beats v11's official trial-0 Elo 1545 (+109).
- Trial 1: Elo **1364** (3W/1D/2L, spare_plies 340).
- Trial 2: terminated externally (SIGTERM mid-run), not completed.
  Official grade is trial 0 only.
