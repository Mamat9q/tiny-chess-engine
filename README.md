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
