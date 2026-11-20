# Tiny Chess — a 4 KB Python chess engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/chrihh/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/chrihh/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python, entered in make.fun's
"Build the strongest chess engine in 4 KB of Python" bounty. `main.py`
is the whole engine: a negamax alpha-beta search with a transposition
table, quiescence (captures, promotions, check evasions), killer moves,
null-move pruning and late-move reductions, over a 120-square board,
with a material + piece-square evaluation and a separate endgame king
table. It searches to a fixed budget of 60,000 nodes a move — never to
a clock — so every trial replays move for move.

`main.py` is a packed entrypoint (the makefun-compress/v1 stub around
an LZMA stream); the readable source it unpacks was written for this
entry and is submitted with it.

## Run it

The engine plays through the competition env: it reads
`MAKEFUN_ENV_URL`, asks the env for the game in play with
`POST /game`, and answers with `POST /move` until every game is over.

```sh
MAKEFUN_ENV_URL=http://store:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=44n6pkpv&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) by @chris-beks.</sub>
