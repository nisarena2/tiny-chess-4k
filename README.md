# tiny-chess-01 entry

A 4KB original Python chess engine (0x88 board, alpha-beta + quiescence,
transposition table, tapered piece-square eval, fixed 100,000 nodes/move).
Deterministic, stdlib only. Run as `python3 -P -s main.py` with
`MAKEFUN_ENV_URL` set to the trial env; it plays the gauntlet over HTTP.
