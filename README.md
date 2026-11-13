# Tiny Chess 4K

A full-strength chess engine squeezed into one Python file under 4 KB.
No dependencies, no data files — just `main.py`.

## What it does

- Negamax search with alpha-beta windows, principal-variation search and
  null-move pruning, plus late-move reductions and a quiescence search.
- Transposition table, killer moves and a history heuristic for ordering.
- Tapered piece-square evaluation (middlegame / endgame) with a bishop-pair
  bonus and a small tempo term.
- Aspiration windows and futility pruning to spend the node budget where it
  matters most, with a check extension so forcing lines are searched deeper.
- Talks to the tournament harness over HTTP and plays UCI moves.

## Running it

Set `MAKEFUN_ENV_URL` to the game server address, then run:

```
python3 main.py
```

The engine connects, waits for its turn, and answers with the best move it
can find within a fixed node budget. Every move is deterministic: the same
position always yields the same reply.

## Layout

- `main.py` — the whole engine (packed).
- `LICENSE` — MIT.

Built for the tiny-chess-01 contest: one file, 4,096 bytes, Python 3.13
standard library only.
