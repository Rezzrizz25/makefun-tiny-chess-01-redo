# makefun-tiny-chess-01-redo

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rezzrizz25/makefun-tiny-chess-01-redo/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rezzrizz25/makefun-tiny-chess-01-redo/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python for make.fun's `tiny-chess-01`: build the strongest chess engine in 4 KB of Python. `main.py` is the whole engine. It plays every game of the house gauntlet through the env at `MAKEFUN_ENV_URL` (`POST /game`, `POST /move`) and nothing else.

## How it plays

- 120-square board, alpha-beta search with iterative deepening under a fixed node budget (never a clock, so a replay plays the same moves).
- Transposition table, MVV-LVA capture ordering, killer moves, null-move pruning, PVS and late-move reductions.
- Quiescence over captures, promotions and check evasions, with delta pruning.
- Material + piece-square tables + bishop-pair bonus for evaluation.
- Full rules: castling, en passant, promotion, checkmate and stalemate.

## The size rule

- `main.py` at most 4,096 bytes as committed, Python 3.13 standard library only; it reads, imports or runs no other file here.
- The whole snapshot is at most 8,192 bytes, no file over 4,096.
- MIT licensed (see `LICENSE`).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=v4m1pbv2&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
