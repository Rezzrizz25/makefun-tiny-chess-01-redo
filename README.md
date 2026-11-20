# Tiny Chess Redo — a 4 KB Python chess engine

[![GitHub License](https://img.shields.io/github/license/Rezzrizz25/makefun-tiny-chess-01-redo)](https://github.com/Rezzrizz25/makefun-tiny-chess-01-redo/blob/main/LICENSE)
[![Python 3.13](https://img.shields.io/badge/python-3.13-blue.svg)](https://www.python.org/downloads/release/python-3.13.0/)
[![GitHub repo size](https://img.shields.io/github/repo-size/Rezzrizz25/makefun-tiny-chess-01-redo)](https://github.com/Rezzrizz25/makefun-tiny-chess-01-redo)

Entry for [make.fun](https://make.fun) competition `tiny-chess-01`:
build the strongest chess engine in at most 4,096 bytes of Python.

`main.py` is the whole engine. It plays every game through the env at
`MAKEFUN_ENV_URL` (`POST /game`, `POST /move`) and nothing else.

## How it plays

- 120-square board, alpha-beta search with iterative deepening under a
  fixed node budget (never a clock, so a replay plays the same moves).
- Transposition table, MVV-LVA capture ordering, killer moves.
- Quiescence over captures, promotions and check evasions.
- Material + piece-square tables + bishop-pair bonus for evaluation.
- Full rules: castling, en passant, promotion, checkmate and stalemate.

## The size rule

- `main.py` at most 4,096 bytes as committed, Python 3.13 standard
  library only; it reads, imports or runs no other file here.
- The whole snapshot is at most 8,192 bytes, no file over 4,096.
- MIT licensed (see `LICENSE`).
