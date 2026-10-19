# Roadmap — Java Chess

| # | Milestone | Outcome | Status | Depends on | Risk |
| --- | --- | --- | --- | --- | --- |
| 1 | Playable human vs human | Two players finish a legal game in one Swing window; perft matches known counts | todo | — | Move-gen bugs |
| 2 | AI plays legal moves | AI replies with a legal move, UI stays responsive | todo | 1 | Search lag |
| 3 | Smooth full game | Depth 3–4 reply, no freeze, no allocation in search | todo | 2 | Slow move gen |

## Details

### 1. Playable human vs human
- Done when: `int[64]` board + make/unmake; castling, en passant, promotion; check/checkmate/stalemate; click-to-move rejects illegal moves; perft passes on a known position; runs from one jar.
- Tasks: board + move gen; make/unmake; perft test; Swing board + Unicode render with shape fallback; click-to-move + legality.
- Unknowns: which perft position/depth to use as the baseline.

### 2. AI plays legal moves
- Done when: minimax + alpha-beta picks only legal moves, runs on a worker thread, board repaints once per move.
- Tasks: material + piece-square eval; alpha-beta search; iterative deepening with time cap; off-EDT worker; AI vs human toggle.
- Unknowns: depth vs time cap that stays smooth.

### 3. Smooth full game
- Done when: depth 3–4 reply without freezing; no allocation inside search; one repaint per move; full game to checkmate or stalemate.
- Tasks: move ordering; make/unmake in search; measure node rate; remove allocations; final playtest.
- Unknowns: acceptable reply time on the slowest machine you test.

Next up: 1 — Playable human vs human.
