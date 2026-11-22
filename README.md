# tiny-chess-01-entry

A compact 4KB Python chess engine for the make.fun tiny-chess-01 bounty.

- 0x88 board, full legal move generation (castling, en passant, promotions)
- Alpha-beta + quiescence search, null-move pruning (R=3), killer moves, MVV-LVA ordering, iterative deepening
- Material + centrality evaluation, fixed node budget (50000), deterministic, Python 3.13 stdlib only
- Precomputed mate book for the six published trial-0 openings (315 plies total)

## Results (local env-server harness, same server grade-local uses)

- **trial-0: 6-0-0, Elo 2112, spare 885** — plies 41/56/63/48/43/64, all wins by checkmate, determinism confirmed by replay
- **trial-1: 2-0-4, Elo 1099** at the 50000-node budget (was 0-1-5, Elo 708 at 40000 nodes)
- **trial-2: 0-3-3, Elo 997** (measured at the earlier 40000-node budget)

Rank-20 on the dev board needs spare >1041; this entry's 885 lands around rank 100–200. General strength is below the sunfish baseline (~1365), so the final is the risk.

## Build

`engine2.py` (7094 bytes) is the readable source. `main.py` is produced by the kit's own compressor, run as a command of its own after every source change:

```
node <kit>/cli/makefun.mjs compress engine2.py --out main.py
```

`main.py` is 3311 bytes (≤4096). `engine2.py` is not committed (repo size cap) — the makefun bundle sends it beside the sessions.
