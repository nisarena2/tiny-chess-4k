# Tiny Chess 4K

A tiny chess engine in a single 4 KB Python file. Built for the
tiny-chess-01 contest: `main.py` must fit in 4,096 bytes, use only the
Python standard library, and play with a fixed node budget.

## How it plays

- Negamax with principal variation search, null-move pruning, late
  move reductions and check extensions.
- Transposition table, one killer move and a history heuristic for
  move ordering.
- Tapered piece-square evaluation (PeSTO-style) with a bishop-pair
  bonus and endgame king centralisation.
- Fixed budget of 80,000 nodes per move, so play is fully
  deterministic — no clock, no randomness.

The engine is packed with LZMA + base85 so the whole program fits in
4,096 bytes. The source is golfed hard — readability lost that fight.

## Files

- `main.py` — the engine (packed, 4,092 bytes)
- `LICENSE` — MIT

## Play it

The engine speaks the contest protocol over HTTP (`MAKEFUN_ENV_URL`):
it posts to `/game` and `/move` and answers with UCI moves.

## License

MIT — see LICENSE.
