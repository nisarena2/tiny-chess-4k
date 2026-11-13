# Tiny Chess 4K

A complete chess engine squeezed into one 4 KB Python file, written for
the tiny-chess-01 contest. The whole program — board, search, evaluation
and the match driver — lives in `main.py`, packed with LZMA and base85 so
it stays under the 4,096-byte limit.

## How it plays

The engine uses a 0x88 board and a negamax search with alpha-beta
pruning, principal-variation search, null-move pruning, late-move
reduction, a transposition table, quiescence search and a tapered
piece-square evaluation with a 4-bit packed table. It spends a fixed
budget of 80,000 nodes per move, so every game is fully deterministic:
same position, same move, no clock, no randomness.

The driver talks to the contest environment over HTTP: it polls for the
next game state and answers with the best move in UCI notation until the
game is done. No other files are needed at run time — `main.py` alone is
the engine, standard library only, on Python 3.13.

## Files

- `main.py` — the engine (4,094 bytes)
- `LICENSE` — MIT

Built and tuned by hand, one idea at a time, with perft positions and
practice matches against the house gauntlet to check every change.
