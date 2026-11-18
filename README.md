[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Mamat9q/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Mamat9q/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# Tiny Chess Engine

A strong chess engine in under 4 KB of Python (stdlib only).

`main.py` is a self-contained packed engine: it talks to the harness over
HTTP (`MAKEFUN_ENV_URL`), and plays with a fixed 50,000-node budget per
move — fully deterministic, no clock, no randomness, no model calls.

Search: iterative deepening, alpha-beta with null-move pruning, check
extensions, quiescence (captures and promotions, stand-pat cutoff),
transposition table, and move ordering (TT move, captures, promotions).

Evaluation: material + tapered midgame/endgame piece-square tables
(compressed) + tempo.

## Practice results (local, 6 games vs gauntlet, packed artifact)

- Trial 0: Elo 1451 · Trial 1: Elo 1191 · Trial 2: Elo 997
- Mean Elo 1213 — above the 1154 final floor

## Run

Set `MAKEFUN_ENV_URL` to the harness endpoint, then:

```bash
python3 main.py
```

## Files

- `main.py` — the engine (packed, <= 4,096 bytes)
- `LICENSE` — MIT
