# Plan — Java Chess

Stack: Java 17, Swing, no dependencies, single jar.

## Steps

1. Board representation: `int[64]`, move gen
2. Make/unmake + perft test
3. Swing board + Unicode piece rendering
4. Click-to-move + legality checking
5. AI search off the EDT
6. Polish

## Risks / unknowns

- Slow move gen makes depth-4 search laggy. Fix: make/unmake on one board, move ordering, iterative deepening with a time cap, search on a worker thread.
- Some fonts lack chess glyphs, pieces show as boxes. Fix: check glyph support at startup, fall back to drawn shapes.
- Search must not allocate; board copies per move freeze the UI.
- "Smooth" needs one repaint per move, no per-frame timers.

## Notes

- Rules correctness before UI: the GUI should never chase phantom bugs.
- AI last, since it depends on the rules engine and the UI.
