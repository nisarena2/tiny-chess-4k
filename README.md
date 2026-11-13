# Tiny Chess 4K

A tiny chess engine squeezed into a single 4,096-byte file. It plays through
the make.fun environment server: the server sends a position, the engine
answers with its best move, and the game continues until it ends.

## How it plays

- Negamax search with alpha-beta pruning and principal variation search
- Null-move pruning, late move reductions, and check extensions to look
  deeper where the position demands it
- Quiescence search so a capture on the horizon cannot fool the evaluation
- A transposition table plus killer moves and a history table to order moves
- Tapered piece-square evaluation in the style of PeSTO, a bishop-pair
  bonus, and a small tempo bonus
- A fixed node budget per move, so thinking time stays predictable

## Running it

The engine talks to the environment at the URL in `MAKEFUN_ENV_URL`. Start
it with a position and it keeps answering moves until the game is over.

## Limits

- `main.py` is at most 4,096 bytes and the whole repo at most 8,192
- Python 3.13 standard library only, no randomness, no clock-based choices
- Fully deterministic: the same position always gets the same answer
