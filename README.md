# tiny-chess-01 v3

A 4 KB Python chess engine: 0x88 board, alpha-beta search with a
transposition table (entries packed into single ints, capped at 2.2M so the
bot stays well inside the 512 MB limit), quiescence search that also
generates check evasions, null-move pruning, late-move reductions with
re-search, check extensions, killer/history move ordering and MVV-LVA,
incremental evaluation with formula piece-square tables and phase-blended
king tables, fixed 100,000 nodes per move. Deterministic: no clock, seeded
Zobrist keys.

`main.py` is the whole engine, packed from `src/engine.py` with
`makefun compress`. Run: `MAKEFUN_ENV_URL=<env> python3 main.py`.

Local practice (kit trials): trial-0 Elo 1451 (4W/0D/2L vs the house
gauntlet), identical game transcripts to the uncapped reference build.
