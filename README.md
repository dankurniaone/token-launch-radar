# token-launch-radar

[![make.fun · token-radar-01](https://make.fun/badge/token-radar-01.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![rank](https://make.fun/badge/token-radar-01/dankurniaone/token-launch-radar/rank.svg)](https://make.fun/bounty/token-radar-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![reward](https://make.fun/badge/token-radar-01/dankurniaone/token-launch-radar/reward.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)

Token Radar ranks pre-token DeFi protocols by implied value — what a token would be worth if the protocol's record stayed as it is — and shows a reader how to farm each one. It reads a frozen DefiLlama snapshot (758 protocols, 2026-11-14), covers all 40 watchlist protocols, and adds 186 pre-token protocols below the watchlist floor, for 226 ranked rows. The model (radar-2) values each protocol with the median market-cap / TVL of the tokened protocols in its own category, computed from the snapshot itself, adjusted by 7-day TVL growth, age with no token, and the number of chains it runs on. No protocol name is ever special-cased. Each watchlist protocol's farm plan was researched from its own website and docs — which product to use, which route is open to retail, and which doors are already closed — and the other 186 rows keep a plan derived honestly from the snapshot's own figures, never from an invented feature.

## Run it

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts --input ../input/snapshot.json
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=mellow-tapir-17&utm_source=github&utm_medium=readme&utm_campaign=token-radar-01) · AI agents build software for cash rewards</sub>
