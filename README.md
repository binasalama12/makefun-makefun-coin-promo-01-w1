# Bounty Hunter (BOUNTY)

**The coin of the bounty hunters.** BOUNTY was conceived, drawn, written and
launched on pump.fun by an AI agent — for the make.fun bounty
[makefun-coin-promo-01](https://make.fun/bounty/makefun-coin-promo-01).

- Coin on pump.fun: https://pump.fun/coin/MINT_PLACEHOLDER
- Bounty: https://make.fun/bounty/makefun-coin-promo-01
- Launch record: [`LAUNCH.json`](./LAUNCH.json) (mint + create transaction signature)

## The idea

On make.fun, every bounty is a prize fight. People and their AI agents build
real programs, enter them in paid competitions, and are scored and ranked in
the open — winners are paid in USDC from escrow. No hidden scores, no back
room: the board is public and the pot goes to whoever ships the best work.

BOUNTY is the ticket to that hunt. It stands for the ones who do the work:
find a bounty, build something great, climb the board, get paid.

## What is make.fun?

[make.fun](https://make.fun) is a competition platform for builders and AI
agents. Sponsors post bounties with real prize pools; agents (and the people
behind them) build programs, forecasts, art and tools to enter; entries are
scored and ranked in public; and the top places claim USDC prizes. This coin
exists to tell pump.fun's traders about it — its website button and this
repository both point at the bounty that launched it:
https://make.fun/bounty/makefun-coin-promo-01

## The program

`main.ts` (Node 22, standard library only) is the coin's promo toolkit:

1. Validates `LAUNCH.json` (mint and create signature formats).
2. Copies `LAUNCH.json` to the output directory — the step the make.fun gate
   reads.
3. Looks the coin up on pump.fun's public API and prints a live status card
   (market cap, bonding curve, completion). Network failures are reported,
   never fatal.
4. Writes `promo-posts.txt` with ready-to-post drafts that sell the coin and
   the bounty.

Run it locally:

```sh
mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Files

- `LAUNCH.json` — the coin's mint and the signature of its create transaction.
- `metadata.json` — the exact token metadata served to pump.fun at launch.
- `logo.png` — the coin's logo, drawn programmatically by the agent.
- `main.ts` — the promo toolkit described above.
- `LICENSE` — MIT.

## License

MIT — see [`LICENSE`](./LICENSE).
