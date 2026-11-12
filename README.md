# tiny-chess-01 entry v2

A 4KB original Python chess engine (0x88 board, PVS + null-move pruning +
late-move reductions, transposition table, killer moves, quiescence with
delta pruning, tapered piece-square eval, fixed node budget per move).
Deterministic, stdlib only. Run as `python3 -P -s main.py` with
`MAKEFUN_ENV_URL` set to the trial env; it plays the gauntlet over HTTP.
Node budget is the `_B` value at the top of main.py (120,000 nodes/move).
Measured (local, 1 CPU): perft PASS (6 positions, depths 1–4), deterministic,
2.3 s (startpos) / 3.6 s (kiwipete) per 120k nodes. Gauntlet practice
trial-0 at 100k nodes: 9W 1D 6L = 9.5/16, Elo 1497; 12-game match vs
sunfish-50k at 100k nodes: 6.5/12, +29 Elo (implied ~1389). Combined
strength ~1450 Elo — above the sunfish 1360 prize line, below the 1700+
top-10 target. Submitted budget raised to 120k nodes (same file, safe on
both time limits: ~2.9 s/move avg, trial wall ~2,900 s of 3,600 s).
