# tiny-chess-01-entry

A compact 4KB Python chess engine for the make.fun tiny-chess-01 bounty.

- 0x88 board, full legal move generation (castling, en passant, promotions)
- Alpha-beta + quiescence search, MVV-LVA ordering, iterative deepening
- PeSTO tapered piece-square evaluation (middlegame tables)
- Fixed node budget, deterministic, Python 3.13 stdlib only

`main.py` is a packed (lzma + base85) single-file engine, 4090 bytes.
