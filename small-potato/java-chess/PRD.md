# Java Chess

Status: planning · Started: 2026-10-19

## What

A chess game in Java 17 with a Swing GUI, one window, no external dependencies, shipped as a single jar.

## Why

A playable chess game that runs anywhere `java` is installed, built to learn game rules, search, and UI threading properly.

## Done when

- [ ] Full move rules: castling, en passant, promotion
- [ ] Check, checkmate, stalemate detected
- [ ] Human vs human works
- [ ] Human vs AI works, AI only plays legal moves
- [ ] Perft test passes on a known position
- [ ] Runs from a single jar with no extra libs

## Success

Games finish correctly: no illegal moves accepted, no missed checkmate, AI responds without freezing the UI.

## Out of scope

- 50-move rule and threefold repetition (v1)
- PGN save/load
- Undo
- Move timer / clocks
- Puzzles
- Online play
- LLM/Groq for move generation (hallucinates illegal moves, needs net + key)

## Decisions

- AI: local minimax + alpha-beta, depth 3–4, material + piece-square eval. Free, offline, no API key.
- Rendering: Unicode chess glyphs behind a renderer interface; shape fallback if font lacks glyphs.
- Smoothness: make/unmake on one `int[64]` board, no allocation inside search, AI on worker thread, one repaint per move.
