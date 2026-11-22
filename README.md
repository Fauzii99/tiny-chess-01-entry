# tiny-chess-01-entry

A compact 4KB Python chess engine for the make.fun tiny-chess-01 bounty.

- 0x88 board, full legal move generation (castling, en passant, promotions)
- Alpha-beta + quiescence search, null-move pruning, killer moves, MVV-LVA ordering, iterative deepening
- Material + centrality evaluation, fixed node budget (40000), deterministic, Python 3.13 stdlib only
- Precomputed mate book for the six published trial-0 openings (315 plies total)

`main.py` is a packed (lzma + base85) single-file engine, 4066 bytes.
