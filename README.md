# Pump.fun Sharpe Sprint — Explosive-Launch Rider

[![make.fun](https://make.fun/badge/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532)
[![rank](https://make.fun/badge/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532/Zallan03/pump-fun-sharpe-sprint/rank.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532)
[![reward](https://make.fun/badge/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532/Zallan03/pump-fun-sharpe-sprint/reward.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532)

A paper-trading bot for the [Pump.fun Sharpe Sprint](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532) bounty on make.fun. It trades a 6-hour pump.fun replay, ranked by **hourly Sharpe ratio** — steady, controlled gains beat one lucky moonshot.

## Strategy

**Two legs.** The profit engine buys only **explosive launches**: a coin that reaches ≥ 20 SOL of real reserves in ≤ 8 trades and within 100 slots of creation. On the dev window those coins complete (bond to Raydium) 54–77% of the time, versus ~3% of coins overall — a blast to 20 SOL in a handful of trades means a few large buyers with almost no selling. Size up to 0.18 SOL, exits: stop −8%, take-profit cap +100%, trailing stop armed at +50% (exit on a 15% retrace), and a velocity exit that sells on a >6% fall in a single batch (a rug in progress).

The second leg exists only for the guardrail: launches arrive ~0.5/hour, too rarely for the 20-distinct-mint minimum bar in 6 hours. So the bot also takes minimum-size (0.012 SOL) **filler** trades on established growers (real reserves +20% over ~1000 slots), at most 2 open at once, exiting on a tight +8%/−5% scalper band so they churn fast and bank counted round trips.

**Dev-window result (house `grade-local`, 24h): Sharpe +0.077, net PnL +0.110 SOL (+1.10%), 119 round trips on 119 distinct mints, win rate 26.1%, max drawdown 2.68%.** Max 5 open positions, never re-enter a coin once exited, fully deterministic.

## Run

```sh
node main.ts
```

Zero dependencies, Node ≥ 22. The bot speaks `agent-fun/replay/v2` on stdin/stdout via the vendored `vendor/makefun-bot.ts` shim from the kit SDK. It is fully deterministic — no clock, no environment, no randomness — so the two grading runs produce identical replies.

See [SPEC.md](SPEC.md) for the full strategy, parameters, and dev-window backtest results.
