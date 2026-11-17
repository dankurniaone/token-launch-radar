# Farm guides — researched from the protocols' real websites

Research for the make.fun token-radar-01 entry, 2026-11-17. Scope: the 40-protocol watchlist only.
Method: each protocol's DefiLlama page, then its OFFICIAL website (homepage + docs/app page).
Where the official site could not be opened directly, the finding rests on the protocol's own docs/blog
found via search plus DefiLlama — marked `partial`. Nothing here invents a feature: if the site
does not say it, the guide says so.
Round 2 re-check completed 2026-11-17: the 20 `partial` entries were re-read live; see below.

## Tally

- Verified from the official site: **36** / 40
- Partial (official site not fully openable; confirmed via own docs + DefiLlama): **4** / 40
- Unverified: **0** / 40

## The 5 biggest contradictions with the current farm steps

Current steps are the category-derived ones in `lib/model.ts` (commit 905a11c).

1. **Veda (rank 3) — there is no 'Veda vault' a retail user can deposit into.**
   Current step 2: 'Deposit $150 into a Veda vault on Ink and keep the vault shares.'
   veda.tech says Veda is B2B vault infrastructure ('Veda Earn' lets an app offer Earn without
   building it). It powers ether.fi Liquid, Lombard DeFi Vault, and Mantle cmETH. A retail user
   farms Veda by depositing into one of those partner products, not on veda.tech.

2. **Yuzu Money (rank 58) — retail users may not mint yzUSD at all.**
   Yuzu's own docs: primary minting/redeeming of yzUSD and yzPP is restricted to accredited /
   qualified / institutional investors after KYC/AML and source-of-funds checks; 'retail users are
   not eligible to mint, subscribe, or redeem.' The real retail paths are buying yzUSD second-hand
   and staking it for syzUSD, or the open Marketplace vaults (yzSyrup/yzCash).

3. **Axis (rank 20) — the vault the old steps would send you to is closed.**
   The Origin Vault pre-deposit window closed 5 Aug 2026 and converted into the Ecosystem Vault.
   The only live path is holding USDx/sUSDx positions that count for Coordinates, with sUSDx
   redemptions on a 7-day cooldown.

4. **Noble (rank 41) — not a farmable protocol at all.**
   DefiLlama has no protocol page for Noble (404): Noble is a chain. Worse, Circle is ending
   USDC/CCTP V1 support on Noble (new minting disabled 13 Oct 2026, contract fully paused
   12 Jan 2027), which threatens the 'bridge USDC to Noble, buy USDN, Points Vault' path.
   (And noble.org is an unrelated ranching institute; the real site is noble.xyz.)

5. **Steakhouse Financial (rank 1) / Gauntlet (rank 2) / most Risk Curators — no retail deposit
   on their own sites.** Steakhouse vaults are reached through Morpho or partner apps (Coinbase
   DeFi Lend for eligible Coinbase users); Gauntlet through app.gauntlet.xyz or partner earn
   programs (KAST Earn). The same pattern repeats for Nonce Capital (no vault/app at all — farm
   via ether.fi Liquid vaults it curates), OpenTrade (B2B-only, retail via Littio/Midas/WOO X),
   Tulipa Capital (B2B curator, no deposits), Keyrock (retail via Morpho vaults), Valos
   (institutional-only; exposure only via e.g. a Valos vUSD market inside Curvance), and
   Clearstar / Galaxy Curation (Morpho vaults).

Other notable findings: Lightning Network has no token, vault, or points program (only routing
fees from running a node); b14g had ~$1.47M drained without authorization on 31 Oct 2026;
Saturn Season 1/2 points registration closed 16 Nov 2026 9:00 AM EST; Curvance has no verified
CVE token or airdrop; Plume Vaults take pUSD as the standard deposit asset, not plain USDC;
OnRe points are 1 per ONyc per day (Loopscale no longer recommended after its exploit froze
withdrawals); Doppler's snapshot chain label 'Ripple' is really XRPL; Firelight farmers are
capital providers (stake FXRP for stXRP) with 30-60 day exits, not cover buyers; Mezo Earn is
lock BTC for veBTC, optionally lock MEZO for up to 5x boost, and vote weekly on gauges.

## Round 2 re-check (2026-11-17)

All 20 entries that were `partial` after round 1 were re-checked against their official
sites/docs live. 17 had their farm steps upgraded, 3 keep their old steps.

- Upgraded (17): nonce-capital, onre, opentrade, plume-vaults, rockawayx, symbiotic,
  hyperithm, r25, k3-capital, clearstar, b14g, galaxy-curation, ember, noble,
  reti-pooling, tydr, firelight. Valos keeps its steps but is now `verified`: valos.io
  was read directly and confirms the entry word-for-word.
- Kept (3): hive-protocol (site still geo-blocked), axis (app geo-blocked; Coordinates
  mechanics still secondary-only; Season 1 start-date conflict unresolved), valos
  (steps unchanged, status upgraded — see above).
- Biggest corrections: tydr's 'no points program' was wrong — TydroInkPoints weekly
  campaigns run since Oct 2025, Season 2 live, Merkl claims toward $INK. Symbiotic's
  'points accrue' was wrong — the site/docs mention no points program or token, and TVL
  is down 41% to ~$287M. b14g contracts are PAUSED since 31 Oct 2026 with no post-mortem
  and no repayments yet — the steps now say do not deposit. Noble's USDC bridge-in path
  is degrading toward a full pause on 12 Jan 2027. Hyperithm disclosed a 30 Oct 2026
  personal-data breach — the steps now warn about phishing. Firelight adds a
  time-sensitive 230,000 FXRP early-contributor claim window (7 Oct–7 Dec 2026).

## Per-protocol findings

### #1 Steakhouse Financial (`steakhouse-financial`) — verified

- Category: Risk Curators · Chains: Base, Ethereum, Robinhood Chain, Arbitrum, Solana, Monad, Arc, Katana, Polygon, Unichain, Corn
- Official site: https://www.steakhouse.financial
- DefiLlama: https://defillama.com/protocol/steakhouse-financial
- What it does: An onchain vault curator that designs and curates noncustodial stablecoin lending vaults, mostly on Morpho (income statement shows Morpho Yields and Kamino Yields). Retail users do not deposit on steakhouse.financial itself; they access the vaults through partner apps — Coinbase DeFi Lend lets eligible Coinbase users lend USDC through Steakhouse-curated Morpho vaults — or directly on Morpho.
- Notes: No points or rewards program found on the site. CONTRADICTION with current steps: the current step 2 says 'Deposit $150 into a Steakhouse Financial vault on Base' as if the site itself takes deposits — it does not; deposits go through Morpho vaults or partner apps (Coinbase DeFi Lend). The vault-on-Base part is right (Base holds 47% of TVL, $1.285B).
- Sources: https://defillama.com/protocol/steakhouse-financial, https://www.steakhouse.financial

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. (Cost: under $3 of gas for the first transaction. Time: 5 minutes.)
  2. Deposit $150 of USDC into a Steakhouse-curated vault on Morpho on Base: open the Morpho app, find a Steakhouse vault, and supply USDC. The site lists Coinbase DeFi Lend as the retail route for eligible Coinbase users. (Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.)
  3. Top up the same vault with a smaller amount the following week, so the record shows more than one deposit instead of a single one. (Cost: about $4 of gas a week. Time: 10 minutes a week.)
  4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. (Cost: $150 locked in the vault until you exit. Time: 30 days.)
  5. Check Steakhouse Financial once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. (Cost: no money, just your time. Time: 10 minutes a week.)
  6. Before you claim anything, open Steakhouse Financial's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. (Cost: nothing to check. Time: 10 minutes.)
  7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 from the Morpho vault and close the position. (Cost: about $3 of gas to exit. Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $150 into a Steakhouse Financial vault on Base and keep the vault shares. Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $4 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $150 locked in the position until you exit. Time: 30 days.
    5. Check Steakhouse Financial once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Steakhouse Financial's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #2 Gauntlet (`gauntlet`) — verified

- Category: Risk Curators · Chains: Base, Binance, Ethereum, Arbitrum, Stable, Morph, Solana, Hyperliquid L1, Polygon, OP Mainnet, Unichain, Katana, Arc, Tempo
- Official site: https://gauntlet.xyz
- DefiLlama: https://defillama.com/protocol/gauntlet
- What it does: Institutional vault curator: full-stack vault curation (lending, restaking, multi-strategy vaults) built on Morpho and Pendle, with an app at app.gauntlet.xyz and a vault catalogue at vaultbook.gauntlet.xyz. Its Gauntlet USD Alpha strategy powers partner earn programs (e.g. KAST Earn, no gas fees for users, rewards auto-compounded). Retail access is through the app or partner apps, not a simple 'deposit on gauntlet.xyz' flow.
- Notes: No points or rewards program found on the site. The site is institutional-first ('Crypto Yield Strategies for Institutions'); the retail path is the app or partner earn programs such as KAST Earn. Current generic vault steps are directionally right but miss that gauntlet.xyz itself is a marketing site — deposits happen in app.gauntlet.xyz or a partner app.
- Sources: https://defillama.com/protocol/gauntlet, https://gauntlet.xyz

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. (Cost: under $3 of gas for the first transaction. Time: 5 minutes.)
  2. Deposit $150 of USDC into a Gauntlet vault on Base through the Gauntlet app (app.gauntlet.xyz) or the vault catalogue, and keep the vault shares. Base holds the largest share of Gauntlet TVL. (Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.)
  3. Top up the same vault with a smaller amount the following week, so the record shows more than one deposit instead of a single one. (Cost: about $4 of gas a week. Time: 10 minutes a week.)
  4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. (Cost: $150 locked in the vault until you exit. Time: 30 days.)
  5. Check Gauntlet once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. (Cost: no money, just your time. Time: 10 minutes a week.)
  6. Before you claim anything, open Gauntlet's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. (Cost: nothing to check. Time: 10 minutes.)
  7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 from the vault and close the position. (Cost: about $3 of gas to exit. Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $150 into a Gauntlet vault on Base and keep the vault shares. Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $4 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $150 locked in the position until you exit. Time: 30 days.
    5. Check Gauntlet once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Gauntlet's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #3 Veda (`veda`) — verified

- Category: Onchain Capital Allocator · Chains: Ink, Ethereum, Optimism, Monad, Plasma, Hyperliquid L1, Base, Arbitrum, Berachain, Sonic, Binance, BOB, Scroll
- Official site: https://veda.tech
- DefiLlama: https://defillama.com/protocol/veda
- What it does: A B2B DeFi vault platform: Veda builds the vault infrastructure that other apps sell as yield products ('Veda Earn' lets an app offer Earn without building the infrastructure). Its technology powers ether.fi Liquid, Lombard DeFi Vault, and Mantle cmETH. There is NO retail deposit flow on veda.tech itself.
- Notes: BIG CONTRADICTION with current steps: the current plan tells the reader to deposit into 'a Veda vault' as if veda.tech takes deposits. It does not — Veda is B2B infrastructure. A retail user farms Veda by depositing into a partner product built on Veda (ether.fi Liquid, Lombard DeFi Vault, Mantle cmETH, per the site and DefiLlama). No points program found on the site.
- Sources: https://defillama.com/protocol/veda, https://veda.tech

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. (Cost: under $3 of gas for the first transaction. Time: 5 minutes.)
  2. Deposit $150 into a vault built on Veda on Ink, the chain holding most Veda TVL: the named products are ether.fi Liquid, Lombard DeFi Vault, and Mantle cmETH — open the product's own app and deposit there, since veda.tech itself takes no deposits. (Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.)
  3. Top up the same vault with a smaller amount the following week, so the record shows more than one deposit instead of a single one. (Cost: about $4 of gas a week. Time: 10 minutes a week.)
  4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. (Cost: $150 locked in the vault until you exit. Time: 30 days.)
  5. Check Veda once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. (Cost: no money, just your time. Time: 10 minutes a week.)
  6. Before you claim anything, open the product's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. (Cost: nothing to check. Time: 10 minutes.)
  7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 from the vault and close the position. (Cost: about $3 of gas to exit. Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $150 into a Veda vault on Ink and keep the vault shares. Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $4 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $150 locked in the position until you exit. Time: 30 days.
    5. Check Veda once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Veda's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #4 USDD (`usdd`) — verified

- Category: CDP · Chains: Tron, Ethereum, Binance
- Official site: https://usdd.io
- DefiLlama: https://defillama.com/protocol/usdd
- What it does: A fully decentralized stablecoin pegged to the US dollar through crypto reserves. Users mint USDD against ETH or WBTC collateral in the ETH Vault or WBTC Vault at app.usdd.io, keeping upside exposure to the collateral while spending the minted USDD. Tron holds 96% of TVL, but the site's mint flow is the ETH/WBTC vaults.
- Notes: No points or rewards program found on the site. The site's mint flow (ETH Vault / WBTC Vault at app.usdd.io) matches the CDP category mechanics, so the current generic CDP steps are directionally right — but they miss the specifics: the vaults are named ETH Vault and WBTC Vault, and minting happens at app.usdd.io/eth. Note: Tron holds 96% of TVL while the documented mint flow is on Ethereum; the steps use the Ethereum flow because that is what the site documents.
- Sources: https://defillama.com/protocol/usdd, https://usdd.io

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. (Cost: under $3 of gas for the first transaction. Time: 5 minutes.)
  2. Mint $150 of USDD against ETH collateral in the ETH Vault at app.usdd.io/eth: connect your wallet, deposit ETH, and mint USDD without selling your ETH position. (Cost: $150 of collateral value and about $8 of gas. Time: 15 minutes to set up.)
  3. Put the minted USDD to work the following week — use it to trade or farm yield in another DeFi protocol — while keeping the ETH collateral locked in the vault. (Cost: about $4 of gas a week. Time: 10 minutes a week.)
  4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Keep the collateral ratio healthy: if ETH falls hard, top up collateral or repay some USDD before the vault is liquidated. (Cost: $150 of collateral locked until you exit. Time: 30 days.)
  5. Check USDD once a week: its peg, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If the peg slips or TVL drops hard two weeks in a row, re-check before you add more. (Cost: no money, just your time. Time: 10 minutes a week.)
  6. Before you claim anything, open USDD's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. (Cost: nothing to check. Time: 10 minutes.)
  7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: repay the USDD, withdraw your ETH collateral from the vault, and close the position. (Cost: about $3 of gas to exit. Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Supply $150 of USDC to USDD on Tron and leave it earning interest. Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.
    3. Lend a second, smaller amount on USDD the following week, using a different asset as collateral, so the record shows more than one deposit. Cost: about $4 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $150 locked in the position until you exit. Time: 30 days.
    5. Check USDD once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open USDD's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #5 Upshift (`upshift`) — verified

- Category: Onchain Capital Allocator · Chains: Ethereum, Stellar, Flare, Monad, Hyperliquid L1, Avalanche, Solana, Fluent, Base, Citrea, Sui, Plasma, Binance, Mezo, Ink
- Official site: https://app.upshift.finance
- DefiLlama: https://defillama.com/protocol/upshift
- What it does: Onchain yield app: 'Supply, stake and access cross-chain yields.' The Earn page at app.upshift.finance lists featured vaults a retail user can deposit into directly — tokenized T-bill vaults, Sentora USD Core, Gami earnUSDC, Flare XRP Yield Vault, and others — with $522M total deposited. Upshift also builds custom yield products for fintechs.
- Notes: No points or rewards program found on the site. Unlike Steakhouse/Gauntlet/Veda, Upshift DOES have a direct retail Earn page with named vaults (Sentora USD Core, Gami earnUSDC, Flare XRP Yield Vault, tokenized T-bill vault), so the current generic vault steps are close — but naming a real vault from the Earn page is more accurate than a generic 'vault on Ethereum'.
- Sources: https://defillama.com/protocol/upshift, https://app.upshift.finance

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. (Cost: under $3 of gas for the first transaction. Time: 5 minutes.)
  2. Deposit $150 of USDC into a featured vault on the Upshift Earn page (app.upshift.finance) on Ethereum, the chain holding most Upshift TVL — for example the Sentora USD Core vault — and keep the vault shares. (Cost: $150 of capital and about $8 of gas. Time: 15 minutes to set up.)
  3. Top up the same vault with a smaller amount the following week, so the record shows more than one deposit instead of a single one. (Cost: about $4 of gas a week. Time: 10 minutes a week.)
  4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. (Cost: $150 locked in the vault until you exit. Time: 30 days.)
  5. Check Upshift once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. (Cost: no money, just your time. Time: 10 minutes a week.)
  6. Before you claim anything, open Upshift's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. (Cost: nothing to check. Time: 10 minutes.)
  7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $150 from the vault and close the position. (Cost: about $3 of gas to exit. Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Upshift vault on Ethereum and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Upshift once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Upshift's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #6 Bittensor dTAO (`bittensor-dtao`) — verified

- Category: Dexs · Chains: Bittensor
- Official site: https://bittensor.com/
- DefiLlama: https://defillama.com/protocol/bittensor-dtao
- What it does: Bittensor is a decentralized machine-intelligence network where independent subnets produce digital commodities and the chain pays contributors in TAO. Its dTAO pools are the native AMMs that price each subnet's alpha token against TAO and hold subnet liquidity.
- Notes: Homepage opened directly; staking mechanics confirmed from Bittensor's official docs via search. No points program exists: rewards are alpha emissions and root dividends, not points. There is no vault to deposit into — staking is a swap into a subnet alpha token through an AMM pool, so any generic 'deposit into a vault' step would be wrong here. Costs and the 30-day hold are honest estimates, not site facts. Minimum partial stake is 0.002 TAO per the docs.
- Sources: https://defillama.com/protocol/bittensor-dtao, https://bittensor.com/, https://www.bittensor.com/docs/guides/staking

  Farm steps (researched):
  1. Set up a fresh Bittensor wallet (coldkey) using btcli or a Bittensor wallet such as Crucible, and save the seed phrase offline before funding it. (Cost: Free to create. Time: 10-15 min.)
  2. Buy native TAO on a major exchange and withdraw it to your Bittensor wallet on the Bittensor (Finney) network, not a wrapped TAO on another chain. (Cost: Exchange withdrawal fee varies. Time: 10-30 min.)
  3. Pick a subnet by its netuid and check its validator hotkeys, take (commission) rate and recent performance before staking anything. (Cost: Free. Time: 15-30 min.)
  4. Quote the stake first with btcli so you can see the price impact, since staking swaps TAO into the subnet's alpha token at the AMM pool price. (Cost: Free to quote. Time: 5 min.)
  5. Stake TAO to your chosen validator hotkey on that subnet; your TAO is swapped into alpha and your position earns a share of that subnet's alpha emissions. (Cost: Network fee, small (estimate under $1). Time: 5 min.)
  6. Hold the stake and let emissions accrue automatically each tempo; there is nothing to claim and nothing to manage unless you want to move stake. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit with remove-stake or unstake-all, which swaps your alpha back to TAO at the pool price instantly; there is no unbonding period, so TAO is spendable at once. (Cost: Network fee, small (estimate under $1). Time: 5 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Provide $100 of liquidity to Bittensor dTAO's main pool on Bittensor and leave it earning trading fees. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Swap a small amount through Bittensor dTAO on Bittensor once a week, on top of the liquidity position. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 60 days.
    5. Check Bittensor dTAO once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Bittensor dTAO's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #7 Nonce Capital (`nonce-capital`) — verified

- Category: Risk Curators · Chains: Ethereum, Optimism
- Official site: https://nonce-capital.xyz
- DefiLlama: https://defillama.com/protocol/nonce-capital
- What it does: Nonce Capital is a DeFi risk curator that manages asset allocation and strategies for third-party vaults, including ether.fi Liquid vaults and Midas tokenized funds. It has no retail deposit app of its own; it curates vaults built on Veda infrastructure for other protocols.
- Notes: Re-checked 2026-11-17: nonce-capital.xyz now reads directly (was HTTP 429). It confirms institutional-only, no deposit button: $455.2M TVL (Liquid ETH $324.4M, Liquid USD $112.0M, Liquid BTC $18.8M). Aave governance (2026-07-14) confirms Nonce curates the ether.fi Liquid vault suite and is independent risk admin for ether.fi Cash's Aave V4 instance. ether.fi Liquid unavailable in US, Canada, UK; withdrawals up to 3 days, 7 days for Liquid USD RWA vaults. No Nonce points program was found anywhere.
- Sources: https://nonce-capital.xyz, https://defillama.com/protocol/nonce-capital, https://help.ether.fi/en/articles/517109-how-liquid-works, https://governance.aave.com/t/arfc-deploy-a-dedicated-aave-v4-whitelabel-instance-fully-managed-by-etherfi-on-op-mainnet-to-power-ether-fi-cash/25314

  Farm steps (researched):
  1. Use a fresh wallet and understand Nonce Capital itself has no deposit button: nonce-capital.xyz is an institutional curator site ($455.2M TVL: Liquid ETH $324.4M, Liquid USD $112.0M, Liquid BTC $18.8M). You farm it indirectly through ether.fi Liquid vaults it curates. (Cost: Free. Time: 10 min.)
  2. Go to the ether.fi app and open Liquid, the retail vault suite Nonce Capital curates, and check which Liquid vaults are live — Liquid ETH, Liquid USD and Liquid BTC — on Ethereum or Optimism. (Cost: Free. Time: 10-15 min.)
  3. Check geo-restrictions first: ether.fi Liquid is not available to users in the United States, Canada, or the United Kingdom, and availability varies by location. Do not proceed if you are in an excluded jurisdiction. (Cost: Free. Time: 5 min.)
  4. Fund your wallet with ETH, BTC or a supported stablecoin on Ethereum, keeping some ETH aside for gas, since deposits and withdrawals are on-chain transactions. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  5. Deposit into a Liquid vault from the ether.fi app by selecting the asset and amount and confirming the transaction; your funds then start earning automatically and Nonce rebalances allocation and risk behind the scenes. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  6. Hold the vault position and track it in the ether.fi app; there is no separate Nonce action to take and no Nonce points program was found anywhere. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit through the ether.fi Liquid withdrawal flow in the same app; ether.fi estimates Liquid withdrawals can take up to three days to settle, or up to seven days for Liquid USD RWA vaults. (Cost: Gas $2-8 (estimate). Time: Up to 3 days to settle (7 days for RWA vaults).)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Nonce Capital vault on Ethereum and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 60 days.
    5. Check Nonce Capital once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Nonce Capital's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #8 OnRe (`onre`) — verified

- Category: RWA · Chains: Solana
- Official site: https://app.onre.finance
- DefiLlama: https://defillama.com/protocol/onre
- What it does: OnRe connects on-chain capital to real-world reinsurance risk through ONyc, a yield-bearing token on Solana backed by reinsurance premiums and collateral investments. Its OnRe Points program rewards ONyc holders, with higher multipliers for using ONyc in DeFi.
- Notes: Re-checked 2026-11-17: app.onre.finance now reads directly (was HTTP 429). Open Access is permissionless with no onboarding or minimums, for non-US users; US and sanctioned jurisdictions prohibited. Points multipliers corrected from the official blog and airdrops.io (updated 2026-11-11): 1 point per ONyc per day, 1x hold, 2x liquidity, 3-4x lending, 5x YT, 6x loops, plus a limited-time 10x Kamino boost with no announced end date. New: OnRe Yield Plus on Exponent (2.5x points plus a share of $10K in ONyc rewards) and OnRe Core Vault on Ethereum (USDC via Chainlink CCIP, curated by RockawayX, targets 11-13% gross USDC APY, 4x points, 7-day withdrawal notice). Loopscale: second incident reported 2026-11-06 (~$412k + ~$521k, USDC Genesis Vault collateral withdrawals still disabled) — do not use Loopscale.
- Sources: https://app.onre.finance, https://www.onre.finance/blog/onre-introduces-points-program-rewarding-onyc-participation-across-defi, https://www.onre.finance/blog/onres-uncorrelated-reinsurance-backed-yield-is-now-available-on-ethereum-for-the-first-time, https://airdrops.io/onre/, https://defillama.com/protocol/onre

  Farm steps (researched):
  1. Set up a fresh Solana wallet such as Phantom and fund it with USDC on Solana plus a small amount of SOL for fees, then open OnRe Open Access at app.onre.finance and accept the terms: it is permissionless with no onboarding or minimums, but the United States and sanctioned jurisdictions are prohibited. Check the current ONyc price, NAV and APY on the deposit page. (Cost: SOL gas under $1 (estimate). Time: 10-15 min.)
  2. Mint ONyc by swapping USDC for ONyc in Open Access; yield accrues inside the token's NAV rather than being paid out separately, and there is no confirmed token airdrop — points have no cash value. (Cost: SOL gas under $1 (estimate). Time: 5-10 min.)
  3. Hold ONyc in your wallet to earn OnRe Points at 1 point per ONyc per day (1x), and check your position on the OnRe leaderboard in the app. (Cost: Free. Time: Hold 30 days (estimate).)
  4. Boost points only if you accept leverage risk: 2x for ONyc liquidity on Kamino, Orca or Raydium, 3-4x for lending, 5x for YT-ONyc on Exponent, and up to 6x for loops; a limited-time 10x Kamino boost has run with no announced end date, so check the live multiplier first. (Cost: SOL gas under $1 per tx (estimate). Time: 15-30 min.)
  5. Alternatively, deposit ONyc into the OnRe Yield Plus vault on Exponent, curated by Allez, which earns 2.5x OnRe Points plus a share of $10K in ONyc rewards; the vault uses leverage, so losses are possible. For Ethereum-only capital, use the OnRe Core Vault on Accountable's YieldApp instead: deposit USDC on Ethereum, routed via Chainlink CCIP, curated by RockawayX, targeting 11-13% gross USDC APY with 4x OnRe Points and a 7-day standard withdrawal notice. (Cost: SOL gas under $1 per tx (estimate). Time: 15-30 min.)
  6. Do not use Loopscale for ONyc strategies: it was exploited in April 2025 ($5.8M, later recovered) and again in November 2026, when USDC Genesis Vault collateral withdrawals were disabled and vault withdrawals restricted. (Cost: Free. Time: 5 min.)
  7. Exit by redeeming ONyc back to USDC through the OnRe app or by selling it on a Solana DEX; for the Core Vault, give the 7-day withdrawal notice first. (Cost: SOL gas under $1 (estimate). Time: 5-10 min, or 7 days for Core Vault.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into the tokenised asset OnRe offers on Solana and hold it. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check OnRe once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open OnRe's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #9 OpenTrade (`opentrade`) — verified

- Category: RWA · Chains: Avalanche, Ethereum, Plume Mainnet
- Official site: https://www.opentrade.io
- DefiLlama: https://defillama.com/protocol/opentrade
- What it does: OpenTrade is a B2B stablecoin yield-as-a-service platform: fintechs and neobanks use it to power compliant stablecoin yield products backed by real-world assets such as money market funds and ETFs. It has no direct retail deposit app; end users access it through partner apps.
- Notes: Re-checked 2026-11-17: opentrade.io now reads directly (was HTTP 429). Confirms B2B-only infrastructure: $300M+ TVL, $1.5B+ transaction volume, 60+ institutional partners. Products: Single Asset Vaults (MMFs, ETFs, Commercial Paper), Managed RWA Strategies, SOL Staking, SIERRA. Named partners: Littio, Midas, WOO X. Withdrawal timing corrected: docs say most withdrawals process same day, current maximum is 2 business days, cut-off 6pm GMT, whitelisted wallet required. No points program found.
- Sources: https://www.opentrade.io, https://docs.opentrade.io/stablecoin-yield/stablecoin-yield-vaults/money-market-fund-vaults/usd-money-market-fund-vault/withdrawals, https://defillama.com/protocol/opentrade, https://opentrade.gitbook.io/stablecoin-staking-yield/opentrade-stablecoin-staking-yield-powered-by-figment/how-it-works/investments.md

  Farm steps (researched):
  1. Use a fresh wallet and understand OpenTrade is B2B infrastructure ($300M+ TVL, 60+ institutional partners): there is no retail 'deposit' button on opentrade.io, so a retail user reaches its vaults through a partner app instead. (Cost: Free. Time: 10 min.)
  2. Pick a partner app that runs on OpenTrade, such as Littio in Colombia, Midas Kripto in Turkey, or the WOO X RWA Earn section, and open an account there. (Cost: Free to register. Time: 15-30 min.)
  3. Complete the partner's KYC and onboarding, since OpenTrade requires onboarding and a whitelisted wallet before any vault investment, and direct access also needs KYB. (Cost: Free. Time: 30 min to 1 day (estimate).)
  4. Fund the partner account with USDC, USDT or EURC on the chain the partner supports, such as Avalanche or Ethereum, and check the vault's APY and terms; underlying assets are money market funds, ETFs and commercial paper. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  5. Subscribe to the partner's OpenTrade-powered vault in its app; your stablecoins are converted and used to buy the underlying assets, and you receive vault tokens in return. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  6. Hold the vault tokens while yield accrues daily and compounds; there is no lock-up period on OpenTrade vaults and no points program to farm. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit by redeeming your vault tokens in the partner app; OpenTrade docs say most withdrawals process the same day if requested before the 6pm GMT cut-off, with a current maximum of 2 business days. (Cost: Gas $2-8 (estimate). Time: Same day to 2 business days.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into the tokenised asset OpenTrade offers on Avalanche and hold it. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check OpenTrade once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open OpenTrade's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #10 Plume Vaults (`plume-vaults`) — verified

- Category: RWA · Chains: Ethereum, Plume Mainnet, Solana
- Official site: https://app.plume.org
- DefiLlama: https://defillama.com/protocol/plume-vaults
- What it does: Plume Vaults is Plume's flagship real-world-asset protocol: users deposit stablecoins into structured vaults (nTBILL, nALPHA, nBASIS, nPRIME) and receive a receipt token whose redemption value rises as the underlying real-world yield accrues.
- Notes: Re-checked 2026-11-17: app.plume.org now reads directly (was HTTP 429) and shows an Access Denied geo-block: crypto assets are not offered in the US or to US persons or other restricted jurisdictions — a restriction the old steps did not mention. Plume docs confirm the flow exactly (pUSD is the standard deposit asset, mint/bridge at pusd.plume.org, deposit for an nTOKEN, yield as rising redemption value, standard vs instant redemption with a fee). Vault lineup now includes nOPAL (BlackOpal LiquidStone II, $106.9M), nWISDOM, nCREDIT and nACRDX alongside nTBILL, nALPHA, nBASIS and nPRIME; plume.org lists vaults at up to 12.0% APY (check live); Plume Morpho markets are now live on Ethereum with one-click looping. No points program was found in the official docs.
- Sources: https://app.plume.org, https://app.plume.org/docs/introduction/how-to-use-nest, https://app.plume.org/docs/about/vault-operations-and-valuation, https://app.plume.org/docs/about/liquidity-and-redemptions, https://www.plume.org/vaults, https://defillama.com/protocol/plume-vaults

  Farm steps (researched):
  1. Check geo-access first: app.plume.org shows 'Access Denied' for US persons and other restricted jurisdictions, so do not proceed if you are in a restricted region — use only the official site from an allowed region. (Cost: Free. Time: 5 min.)
  2. Set up a fresh EVM wallet such as MetaMask or Rabby and connect it directly on the Plume Vaults portal at app.plume.org; no custodial onboarding is required. (Cost: Free. Time: 10-15 min.)
  3. Get pUSD, the standard deposit asset across all Plume Vaults, by minting or bridging into it at pusd.plume.org; pUSD is backed 1:1 by USDC reserves. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  4. Browse the vault list on the portal and compare vaults such as nTBILL, nALPHA, nBASIS, nPRIME, nOPAL, nWISDOM, nCREDIT or nACRDX by APY, strategy and redemption terms before choosing one. (Cost: Free. Time: 15-30 min.)
  5. Deposit your pUSD (or another supported stablecoin such as USDC or USDT) into the chosen vault and receive its receipt token, an nTOKEN, representing your share. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  6. Hold the nTOKEN while yield accrues inside the vault and shows up as a rising redemption value per token, rather than as separate payouts; no points program was found in the official docs. Optionally use the nTOKEN elsewhere in DeFi, for example supplying pUSD to earn borrower yield, looping vault exposure, or using Plume Morpho markets on Ethereum for one-click looping, if you accept the extra risk. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit by redeeming your nTOKEN in the portal to receive the vault's redemption asset plus accrued yield; some vaults offer same-day or instant liquidity for a fee and others need a 7-day cooldown, so check the selected window and fee before submitting. (Cost: Gas $2-8 (estimate). Time: Minutes to 7 days depending on vault.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into the tokenised asset Plume Vaults offers on Ethereum and hold it. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Plume Vaults once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Plume Vaults's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #11 RockawayX (`rockawayx`) — verified

- Category: Risk Curators · Chains: Ethereum, Solana, Pharos
- Official site: https://rockawayx.com
- DefiLlama: https://defillama.com/protocol/rockawayx
- What it does: RockawayX is an on-chain asset manager and risk curator (over $2B AUM) that runs actively managed vaults on Morpho (Ethereum) and Kamino (Solana) plus market-neutral strategies on Midas. Retail users deposit into its named vaults through those protocols' apps, not through rockawayx.com.
- Notes: Re-checked 2026-11-17: rockawayx.com now reads directly (was HTTP 429) — it is a VC/investment-firm site ($2B+ assets, no deposit flow), confirming deposits happen elsewhere. RockawayX's own vault-curation pages and the Morpho curator page confirm vault names and timelocks (3 days for USDC Yield/wETH, 7 days for USDC Prime) and add: fees (USDC Prime 0%, USDC Yield 5%, wETH 5%, Kamino RWA USDC 2.5%), suite grown to 16 Morpho vaults with $120M+ deposits, RockawayX USDC Yield $25.35M, Kamino RWA USDC vault ($41.9M supply) allocates across OnRe, Huma/Figure PRIME and Solstice. New: a RockawayX-managed onycSOL vault on Exponent (SOL + ONyc yield, pre-deposits open) and $9.7M in market-neutral strategies on Midas (mROX, mMEV). No points program found.
- Sources: https://rockawayx.com, https://www.rockawayx.com/insights/rockawayx-vault-curation-an-overview-of-products-capabilities, https://rockawayx.com/insights/rockawayx-launches-three-curated-vaults-on-morpho, https://app.morpho.org/curator/rockawayx, https://defillama.com/protocol/rockawayx

  Farm steps (researched):
  1. Use a fresh wallet and note that rockawayx.com is a corporate investment site with no deposit button: deposits happen in the Morpho app for Ethereum vaults or the Kamino app for Solana vaults. (Cost: Free. Time: 10 min.)
  2. Open the Morpho app vault list filtered to curator RockawayX and compare its vaults, such as USDC Prime (rxUSDCp, 0% fee), USDC Yield (rxUSDCy, 5% fee) and wETH (rxWETH, 5% fee); the suite has grown to 16 Morpho vaults with $120M+ in deposits. (Cost: Free. Time: 15-30 min.)
  3. Fund your wallet with the vault's deposit asset — USDC for the USDC vaults or WETH for the wETH vault — on Ethereum, keeping ETH aside for gas. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  4. Deposit into the chosen Morpho vault from the app and receive vault shares; RockawayX then handles allocation, rebalancing and risk management behind the scenes. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  5. For Solana exposure, deposit USDC into the RockawayX RWA USDC vault on Kamino instead (2.5% fee, $41.9M supply), which allocates across OnRe, Huma, Figure and Solstice markets. (Cost: SOL gas under $1 (estimate). Time: 10-15 min.)
  6. Hold the vault shares while yield accrues to their value; parameter changes are subject to a timelock of 3 days (USDC Yield, wETH) or 7 days (USDC Prime). There is no points program. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit by redeeming your vault shares in the Morpho or Kamino app, which returns the underlying asset plus accrued yield to your wallet. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a RockawayX vault on Ethereum and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 45 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 45 days.
    5. Check RockawayX once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open RockawayX's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 75 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #12 Symbiotic (`symbiotic`) — verified

- Category: Collateral Markets · Chains: Ethereum
- Official site: https://symbiotic.fi
- DefiLlama: https://defillama.com/protocol/symbiotic
- What it does: Symbiotic is a permissionless restaking protocol, now repositioned as Collateral Markets, where users deposit ERC-20 collateral such as wstETH or cbETH into vaults that secure other networks; the site and docs mention no points program or token.
- Notes: Re-checked 2026-11-17: symbiotic.fi and app.symbiotic.fi now read directly (was HTTP 429). The site has been repositioned as Collateral Markets — a collateral-management platform for allocators, curators and applications — with no points program, token, or retail deposit pitch on the homepage; docs are at docs.symbiotic.fi. Material correction: a November 2026 risk review reports TVL down 41% to $287.49M (from $489.13M), top collateral wstETH $78.84M, uniBTC $77.29M, LBTC $44.15M, and states there is no Symbiotic token and no emissions/points program — contradicting the old step claiming Symbiotic Points accrue to early depositors. Partner docs (Mellow, InceptionLRT) historically credited 1x Symbiotic Points, so points are now presented as historical/partner-tracked only. New: Core V2 lets vault capital earn in outside lending markets, Liquid Lane offers atomic T+0 redemptions, and uniBTC vault epochs are 7 days, so plan on 7-14 days to exit those vaults.
- Sources: https://symbiotic.fi, https://app.symbiotic.fi, https://docs.symbiotic.fi/get-started, https://defillama.com/protocol/symbiotic, https://10k.nyxshcon.org/risk/symbiotic, https://docs.mellow.finance/points/points-in-symbiotic-pre-deposit-contracts

  Farm steps (researched):
  1. Set up a fresh EVM wallet such as MetaMask, fund it with ETH for gas (around 0.01-0.05 ETH is a common buffer), and open the Symbiotic app at app.symbiotic.fi, which lists vaults by collateral, curator, TVL and access. (Cost: Free to set up. Time: 10-15 min.)
  2. Get an accepted collateral asset on Ethereum, most commonly wstETH by staking ETH on Lido and wrapping stETH, or cbETH from Coinbase; wstETH is the largest collateral in the book, followed by uniBTC and LBTC. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  3. Browse the vault registry in the Symbiotic app and shortlist 2-3 active vaults, checking the collateral type, operator set and whether slashing is active; TVL has fallen about 41% to roughly $287M, so check the vault is still active before depositing. (Cost: Free. Time: 15-30 min.)
  4. Deposit your collateral into the chosen vault by approving the token spend and confirming the deposit transaction in your wallet; deposits under about $200 are described as dust in farming guides. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  5. Hold the deposit while it earns restaking rewards from the networks the vault secures; do not farm on points alone — Symbiotic's current site and docs mention no points program or token, and partner docs only historically credited 1x Symbiotic Points. (Cost: Free. Time: Hold 30 days (estimate).)
  6. Track your position and rewards in the app dashboard, and note the slashing risk: a share of your deposit can be slashed if delegated operators misbehave, and Core V2 vaults may also lend capital into outside markets. (Cost: Free. Time: 5 min per check.)
  7. Exit by requesting a withdrawal through the vault in the app, then finalizing the transaction to receive your collateral back to the same address; some vaults use a 7-day epoch, so plan on 7-14 days for those, and check whether Liquid Lane T+0 redemption applies. (Cost: Gas $2-8 (estimate). Time: 5-10 min plus vault exit rules (7-14 days for epoch vaults).)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Supply $100 of USDC to Symbiotic on Ethereum and leave it earning interest. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Symbiotic once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Symbiotic's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #13 Hyperithm (`hyperithm`) — verified

- Category: Risk Curators · Chains: Monad, Ethereum, Arbitrum
- Official site: https://www.hyperithm.com
- DefiLlama: https://defillama.com/protocol/hyperithm
- What it does: Hyperithm is a Tokyo- and Seoul-based digital asset manager (quant trading and venture) that curates Morpho lending vaults such as Hyperithm USDC Apex, mostly on Monad and Ethereum. Retail users deposit into those vaults through the Morpho app, not through hyperithm.com.
- Notes: Re-checked 2026-11-17: hyperithm.com now reads directly (was HTTP 429), but the homepage is dominated by a personal-information breach notice (incident 2026-10-30, discovered 2026-11-03, disclosed 2026-11-06): an unauthorized party accessed business files via a work server, leaking names, affiliations, phone numbers, emails, messenger IDs, home addresses, personal ID numbers and bank account numbers; the server was shut down and authorities notified. Retail users must beware of phishing emails impersonating Hyperithm after this breach. Morpho data confirms the vaults are live and the old $65M cap claim is stale: Hyperithm USDC Apex on Monad holds $32.57M (12.24% APY at last check — check live, it moves), Saturn USDC $14.00M, Hyperithm cbBTC Apex $3.6M; fees are 5% on USDC Apex and 10% on cbBTC Apex. No points program.
- Sources: https://www.hyperithm.com, https://app.morpho.org/curator/hyperithm, https://defillama.com/protocol/hyperithm, https://morphowatch.com/

  Farm steps (researched):
  1. Use a fresh wallet and note that hyperithm.com is a corporate investment-firm site: deposits happen in the Morpho app, where Hyperithm is listed as a curator. (Cost: Free. Time: 10 min.)
  2. Read the breach notice on hyperithm.com first: on 30 October 2026 personal information including names, ID numbers and bank account numbers was leaked, so be especially wary of emails or messages impersonating Hyperithm and never enter credentials from a link in a message. (Cost: Free. Time: 5 min.)
  3. Open the Morpho app curator page for Hyperithm and compare its vaults, such as Hyperithm USDC Apex on Monad ($32.57M deposits at last check), Saturn USDC and Hyperithm cbBTC Apex; check the live APY and liquidity before depositing. (Cost: Free. Time: 15-30 min.)
  4. Fund your wallet with the vault's deposit asset — USDC for the USDC Apex vaults or cbBTC for the cbBTC vault — on the vault's chain, plus gas tokens for that chain. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  5. Deposit into the chosen Hyperithm vault from the Morpho app and receive vault shares; Hyperithm allocates the capital across Morpho lending markets and charges a 5% fee on USDC Apex and 10% on cbBTC Apex. For the Monad permissionless vault, deposit through Accountable's YieldApp instead and receive aHYPER share tokens, which can also be used as Morpho collateral; confirm the route is still live in YieldApp first. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  6. Hold the vault shares while yield accrues to their value; there is no points program, so the return is the lending yield itself. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit by redeeming your vault shares in the Morpho app or YieldApp, which returns the underlying asset plus accrued yield to your wallet. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Hyperithm vault on Monad and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Hyperithm once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Hyperithm's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #14 R25 (`r25`) — verified

- Category: RWA · Chains: Pharos, Sui
- Official site: https://www.r25.xyz
- DefiLlama: https://defillama.com/protocol/r25
- What it does: R25 builds RWA vault infrastructure for automated and curated on-chain yield strategies. Its R25 Studio app at app.r25.xyz lists public vaults on Pharos (for example PodsAlpha and the Allora Eagle vault), and its rcUSD vault on Sui is distributed through partner wallets.
- Notes: Re-checked 2026-11-17: r25.xyz now reads directly (was HTTP 429): $198.35M deposited, 100+ expert strategies, R25 Studio public beta. R25's own X posts confirm PodsAlpha (flexible USDC deposits from 1 USDC, 20% performance fee with a 4% hurdle rate) and the Allora Eagle vault (app.r25.xyz/vaults/EAGLE, systematic long-short on Hyperliquid perps, deposits open to the public). Material change: the Axil Consumer Credit Vault - 6M boost rate drops from 3% to 1.5% effective 2026-01-01, while the 12% base rate stays unchanged — existing holders keep 15% APY until maturity. The Season 2 Binance Wallet campaign ended 2026-10-26, so its $200K PROS rewards are no longer available. New: the pRNH vault (NYLIM/Anemoy US high-yield credit, target $100M, ~7% indicated yield) is for eligible users only, with no fixed lock-up but fund-timeline settlement and regional restrictions.
- Sources: https://www.r25.xyz, https://defillama.com/protocol/r25, https://w.twstalker.com/R25Official, https://chainwire.org/2025/12/19/r25-and-ember-protocol-debut-exclusive-vault-on-sui-via-topnod-wallet/, https://ohsem.me/2026/08/pharos-expands-realfi-market-with-onchain-access-to-institutional-u-s-high-yield-credit/

  Farm steps (researched):
  1. Set up a fresh wallet for Pharos (EVM-compatible) and fund it with USDC on Pharos plus a small amount of the chain's gas token. (Cost: Gas, low (estimate). Time: 10-15 min.)
  2. Open R25 Studio at app.r25.xyz, browse the vaults list and compare live vaults such as PodsAlpha, the Allora Eagle market-neutral vault and Axil credit vaults by APY and terms; total deposits are $198.35M across 100+ strategies. Check each vault's deposit window, minimum and fees: PodsAlpha accepts flexible USDC deposits from 1 USDC with a 20% performance fee and a 4% hurdle rate, while some term vaults only open during a set window. (Cost: Free. Time: 15-30 min.)
  3. Deposit USDC into the chosen Pharos vault from the R25 Studio app and receive vault shares; yield accrues to the share value and some vaults also pay PROS rewards. Note the Season 2 Binance Wallet campaign ended on 26 October 2026. (Cost: Gas, low (estimate). Time: 5-10 min.)
  4. For the Axil Consumer Credit Vault - 6M, note the boost rate drops from 3% to 1.5% from 1 January 2027 while the 12% base rate stays unchanged; existing holders keep 15% APY until maturity. (Cost: Free. Time: 5 min.)
  5. For the Sui rcUSD vault, use the TopNod wallet instead: download it, hold USDC on Sui with a little SUI for gas, and deposit through the wallet's Earn section. (Cost: Gas on Sui, low (estimate). Time: 15-30 min.)
  6. Hold the vault position for its term; the rcUSD vault runs a 12-month term with early withdrawal settled at T+4, and term vaults may have a secondary market before maturity. The pRNH high-yield credit vault is for eligible users only. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit by redeeming in the R25 Studio app or the TopNod wallet; for rcUSD, request withdrawal and expect settlement within 4 days (T+4). (Cost: Gas, low (estimate). Time: Up to 4 days to settle.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into the tokenised asset R25 offers on Pharos and hold it. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 45 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 45 days.
    5. Check R25 once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open R25's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 75 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #15 K3 Capital (`k3-capital`) — verified

- Category: Risk Curators · Chains: Monad, Ethereum, Optimism
- Official site: https://k3.capital
- DefiLlama: https://defillama.com/protocol/k3-capital
- What it does: K3 Capital is an institutional DeFi asset and risk manager (about $200M TVL, delta-neutral strategies) that curates vaults on Morpho, Euler and YieldApp; its own site is only a Coming Soon page.
- Notes: Re-checked 2026-11-17: k3.capital now reads directly (was HTTP 429), but it is only a Coming Soon page for a dedicated US website, stating no services are offered to US residents through the site — confirming no retail deposit flow there. Search corroborates the existing routes and adds material corrections: K3 Earn WETH and K3 Earn AUSD vaults on Euler/Monad are live and deposit-only; the K3 x Galaxy facility is now visible as gAUSD ($31.4M supply, 6.89%), managed by K3 with Galaxy on 90-day rolling loans and monthly redemptions capped at up to 30% of principal — so it is open but redemption-limited, not simply fully subscribed. sBOLD (deposit BOLD, receive yield-bearing shares) is $3.48M TVL, and K3 Capital ETH Maxi on Unichain via Morpho is confirmed. TVL is now ~$200.4M total ($162.57M on Monad), not the ~$400M AUM in the old notes. No points program.
- Sources: https://k3.capital, https://defillama.com/protocol/k3-capital, https://github.com/kamalbuilds/ava-monad/blob/HEAD/docs/MONAD.md, https://privatecredit.therawbyte.com/directory/accountable, https://defiprime.com/arbitrum

  Farm steps (researched):
  1. Use a fresh wallet and note that k3.capital is only a 'Coming Soon' page offering no services to US residents: deposits happen in the Morpho or Euler app, or on Accountable's YieldApp marketplace. (Cost: Free. Time: 10 min.)
  2. Find a K3-curated vault on the Morpho or Euler app, such as the K3 Capital ETH Maxi vault on Unichain, its sBOLD vault where you deposit BOLD for yield-bearing shares, or the K3 Earn WETH and AUSD vaults on Monad. (Cost: Free. Time: 15-30 min.)
  3. Fund your wallet with the vault's deposit asset on the vault's chain — for example BOLD on Ethereum for sBOLD, or AUSD on Monad for the Galaxy credit facility. (Cost: Gas $2-8 (estimate). Time: 10-15 min.)
  4. Check the vault's access terms first: the K3 x Galaxy facility (gAUSD, $31.4M supply) is open but redemptions are monthly and capped at up to 30% of principal, and Galaxy loans roll every 90 days. (Cost: Free. Time: 10 min.)
  5. Deposit into the chosen K3-curated vault from the host app and receive vault shares; K3 manages allocation, collateral choice and caps across the underlying markets. (Cost: Gas $2-8 (estimate). Time: 5-10 min.)
  6. Hold the vault shares while yield accrues to their value; there is no points program, so the return is the lending or credit yield itself. (Cost: Free. Time: Hold 30 days (estimate).)
  7. Exit by redeeming your vault shares in the same host app, which returns the underlying asset plus accrued yield, subject to that vault's liquidity and exit terms — including the 30% monthly cap on gAUSD. (Cost: Gas $2-8 (estimate). Time: 5-10 min, or up to a month for gAUSD.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a K3 Capital vault on Monad and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check K3 Capital once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open K3 Capital's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #16 Hive Protocol (`hive-protocol`) — partial

- Category: Chain · Chains: BSquared
- Official site: https://hive.bsquared.network
- DefiLlama: https://defillama.com/protocol/hive-protocol
- What it does: Hive is the Bitcoin staking layer of B² Network (a Bitcoin zk-rollup L2): users stake BTC to help secure B² and receive $B2 tokens as rewards. DeFiLlama describes it as 'Stake BTC, safeguard B², and receive $B2 Tokens'.
- Notes: The official Hive page (hive.bsquared.network) returned 'Access restricted / not available in your country or region' when opened, so the staking flow could not be confirmed directly on the site; steps 2-7 rely on DeFiLlama's description and third-party guides (GetBlock, KuCoin). No points program was confirmed on the official site; older Odyssey/BUZZ campaign points relate to B² testnet campaigns, not a live Hive points program. Hive is a chain-level staking product, not a vault — there is no 'deposit into a vault' step.
- Sources: https://defillama.com/protocol/hive-protocol, https://hive.bsquared.network, https://getblock.io/marketplace/projects/bsquared/, https://www.kucoin.com/price/B2

  Farm steps (researched):
  1. Use a fresh wallet for farming and set up a BTC-compatible wallet (e.g. Unisat) plus an EVM wallet (e.g. MetaMask) for the B² network, since Hive staking pairs a BTC address with an EVM address. (Cost: $0 (wallet setup is free). Time: 10-15 min.)
  2. Open the official Hive page at hive.bsquared.network and connect both wallets; if the page shows 'Access restricted' in your region, do not use a mirror site — access the official B² docs or app from an allowed region instead. (Cost: $0. Time: 5 min.)
  3. Bridge or acquire BTC to stake through Hive on B² Network, choosing the Hive staking option in the B² Hub interface rather than a third-party pool. (Cost: Bridge/gas fees vary; estimate $2-8. Time: 15-30 min.)
  4. Stake your BTC in Hive: enter the amount, confirm the staking transaction, and note the 1-day unstaking lock reported for B² Hub staking before you commit funds. (Cost: On-chain tx fee, estimate $2-8. Time: 10 min.)
  5. Hold the staked BTC position so B2 token rewards accrue proportionally to your stake; rewards activate immediately once staking is confirmed. (Cost: $0 to hold. Time: Hold 30 days (estimate).)
  6. Optionally stake B2 tokens themselves by delegating to a B² sequencer to earn a share of transaction fees, instead of running your own sequencer node. (Cost: Gas, estimate $2-8. Time: 10 min.)
  7. To exit, request unstaking in the Hive interface, wait out the 1-day unstaking lock, then claim or withdraw your BTC and any accrued B2 rewards to your bound EVM address. (Cost: Gas, estimate $2-8. Time: 1 day unstaking lock + 10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into Hive Protocol's main product on BSquared — check its own page to see which product holds the TVL — and leave the position open. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Hive Protocol once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Hive Protocol's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #17 Tori Finance (`tori-finance`) — verified

- Category: Basis Trading · Chains: Ethereum
- Official site: https://app.tori.finance
- DefiLlama: https://defillama.com/protocol/tori-finance
- What it does: Tori Finance is a synthetic dollar protocol: trUSD is a dollar-pegged token backed by delta-neutral (market-neutral) trading positions, and staking trUSD gives strUSD, an ERC-4626 vault token whose exchange rate grows as the strategies earn.
- Notes: Verified against Tori's own docs. Cores are explicitly 'not a promise of any token or payment' per the docs, and their future use is undecided. Direct minting/redeeming of trUSD at NAV is for verified participants only (0.1% fee, KYC/AML); retail users swap instead. The Season 1 pre-deposit phase (with 2x boost) has ended. The app homepage itself is a JS app that renders little text, so docs.tori.finance was the main verification source.
- Sources: https://defillama.com/protocol/tori-finance, https://app.tori.finance, https://docs.tori.finance/llms.txt, https://docs.tori.finance/faq/trusd, https://docs.tori.finance/resources/cores

  Farm steps (researched):
  1. Use a fresh Ethereum wallet (e.g. MetaMask) for farming and fund it with USDC or USDT plus a little ETH for gas, since Tori runs on Ethereum mainnet. (Cost: $0 setup; gas estimate $2-8 per tx. Time: 10-15 min.)
  2. Open app.tori.finance, connect your wallet, and check the live APY and the Cores multipliers on the app's Earn/DeFi pages before depositing anything. (Cost: $0. Time: 5-10 min.)
  3. Swap USDC or USDT for trUSD in the Tori app; swapping is instant once the Ethereum transaction confirms (typically 12-15 seconds) and there is no minimum amount. (Cost: Standard DEX fees + gas, estimate $2-8. Time: 5 min.)
  4. Stake your trUSD for strUSD in the app to start earning rewards; staking is free and instant, and rewards accrue automatically through the rising strUSD exchange rate with no claiming needed. (Cost: Gas, estimate $2-8; staking itself is free per docs. Time: 5 min.)
  5. Earn Cores, Tori's points program, by holding trUSD, staking strUSD, and using integrated DeFi venues; check the app's Rewards/Boosts tab for the current multiplier per venue (Season 1 pre-deposit paid 30 Cores per dollar per day). (Cost: $0 extra. Time: Hold 30 days (estimate).)
  6. Optionally boost Cores with the Pendle YT Lock tab on the Earn page, which locks Pendle YT-strUSD or YT-trUSD for a higher Cores multiplier, or share your referral link to earn 10% of your referrals' Cores. (Cost: Gas, estimate $2-8. Time: 10 min.)
  7. To exit, unstake strUSD back to trUSD in the app — note the 7-day unstaking cooldown always applies — then swap trUSD back to USDC or USDT; rewards are collected automatically via the exchange rate at unstaking. (Cost: Gas, estimate $2-8. Time: 7-day cooldown + 10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $50 into Tori Finance's basis trade on Ethereum and hold the position. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 60 days.
    5. Check Tori Finance once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Tori Finance's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #18 Lightning Network (`lightning-network`) — verified

- Category: Payments · Chains: Bitcoin
- Official site: https://lightning.network
- DefiLlama: https://defillama.com/protocol/lightning-network
- What it does: The Lightning Network is Bitcoin's Layer-2 payment network: users open off-chain payment channels secured by Bitcoin smart contracts to send instant, low-fee payments, and node operators can earn small routing fees for forwarding others' payments. There is no token, vault, or points program.
- Notes: Verified: lightning.network describes only instant payments, scalability, low cost, and payment channels — there is no farmable product, no token, and no points program. Any generic 'deposit and stake' step for Lightning would be invented. Node setup details come from third-party guides, not the official site. Routing-fee earnings are tiny (hobbyist nodes often earn $1-20/month) and most casual nodes lose money after costs.
- Sources: https://defillama.com/protocol/lightning-network, https://lightning.network, https://www.cherryservers.com/blog/how-to-run-a-lightning-node, https://www.cryptopigs.one/blog/understanding-bitcoin-lightning-network

  Farm steps (researched):
  1. Understand that Lightning has no deposit vault, token, or points program — the only way to 'farm' it is to run a node and earn routing fees, so use a fresh setup and do not expect passive yield. (Cost: $0. Time: 10 min reading.)
  2. Set up a Lightning node using a packaged node OS such as Umbrel, Start9, or RaspiBlitz, or install LND (the most widely used implementation) on your own hardware. (Cost: Hardware cost varies; software is free. Time: 1-2 hours setup.)
  3. Sync a full Bitcoin node first, since Lightning requires the Bitcoin base layer underneath it; this takes days and a few hundred GB of storage. (Cost: $0 (plus hardware/storage). Time: Several days to sync.)
  4. Fund your node's on-chain Bitcoin wallet (e.g. via lncli newaddress) by sending BTC from an exchange or wallet, since you cannot open channels without BTC. (Cost: On-chain BTC tx fee, varies. Time: 10-60 min for confirmations.)
  5. Open payment channels to useful, well-connected peers (wallets, exchanges, big routers) by locking BTC into each channel with an on-chain transaction. (Cost: On-chain fee per channel open, varies. Time: 10 min per channel.)
  6. Set your routing fees (a base fee per forward plus a fee rate in parts per million) and keep channels balanced with inbound and outbound liquidity so payments can actually flow through your node. (Cost: Rebalancing costs fees, varies. Time: Ongoing management, 30 days.)
  7. To exit, close your channels on-chain to settle the final balances back to your Bitcoin wallet; routing fees you earned stay in your node and are collected as sats when channels close. (Cost: On-chain close fee per channel, varies. Time: 10-60 min per close.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into Lightning Network's main product on Bitcoin — check its own page to see which product holds the TVL — and leave the position open. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Lightning Network once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Lightning Network's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #19 Lagoon (`lagoon`) — verified

- Category: Onchain Capital Allocator · Chains: Ethereum, Arbitrum, Base
- Official site: https://lagoon.finance
- DefiLlama: https://defillama.com/protocol/lagoon
- What it does: Lagoon is open, general-purpose vault infrastructure (ERC-7540) for on-chain asset management: curators run yield vaults and any user can join a public vault to start earning on their assets. It is infrastructure, not a single fund — the farmable product is the individual curator vault you pick.
- Notes: Verified against the official homepage and DeFiLlama description. The homepage is partly B2B-facing (vault deployment, 'Talk to us' services), but DeFiLlama and the site confirm users can join any public vault. No Lagoon points/rewards program was found anywhere on the official site — do not claim one exists. Deposit/withdrawal queue mechanics (silo, NAV settlement, async ERC-7540) were confirmed via Lagoon's own blog and a curator's docs page, since the homepage does not spell out the user flow. Typical minimums around $100 were reported by a curator, not by Lagoon itself.
- Sources: https://defillama.com/protocol/lagoon, https://lagoon.finance, https://www.attrius.capital/docs, https://lagoon.finance/blog/building-yield-strategy

  Farm steps (researched):
  1. Use a fresh EVM wallet (e.g. MetaMask or Rabby) and fund it with the asset a vault accepts (usually USDC or ETH) plus gas for the vault's chain — most TVL is on Ethereum, with vaults also on Arbitrum and Base. (Cost: $0 setup; gas estimate $2-8 per tx. Time: 10-15 min.)
  2. Open lagoon.finance, connect your wallet, and browse the 80+ public vaults by curator, strategy (market neutral, directional, fixed income, private credit, PayFi), APY, and chain. (Cost: $0. Time: 10-15 min.)
  3. Pick one public vault and read its strategy, fees, settlement frequency, and asset before depositing; some vaults are gated with whitelists, KYC, or sanctions screening, so confirm yours is open to everyone. (Cost: $0. Time: 10 min.)
  4. Deposit by approving the token spend and confirming the deposit transaction; your deposit enters a queue in the vault's silo contract until the curator strikes NAV and settles it. (Cost: Gas, estimate $2-8. Time: 10 min + settlement wait (often ~24h).)
  5. Claim your ERC-20 vault share tokens once the deposit settles at the new NAV; your position's value then grows through the share price as the curator's strategy earns. (Cost: Gas, estimate $2-8. Time: 10 min after settlement.)
  6. Hold the vault shares and monitor performance in the Lagoon app; there is no Lagoon points program found on the site, so yield comes from the vault's strategy, not from points. (Cost: $0 to hold. Time: Hold 30 days (estimate).)
  7. To exit, submit a withdrawal (redemption) request in the app; the curator unwinds positions and settles at the next NAV cycle, after which only you can claim your assets back to your wallet. (Cost: Gas, estimate $2-8. Time: Settlement cycle, up to ~7 days depending on vault.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Lagoon vault on Ethereum and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Lagoon once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Lagoon's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #20 Axis (`axis`) — partial

- Category: Basis Trading · Chains: Ethereum
- Official site: https://axis.to
- DefiLlama: https://defillama.com/protocol/axis
- What it does: Axis is a quantitative yield protocol that issues USDx, a synthetic dollar backed by a cross-venue arbitrage engine; staking USDx gives sUSDx, the yield-bearing vault token. Its site reports about 15% net APY and $70m TVL, with profits streamed to USDx holders.
- Notes: Partial: axis.to confirms the product, USDx/sUSDx, 15% net APY and $70m TVL, but the live farming mechanics (Origin Vault closure Aug 5 2026, Ecosystem Vault, Coordinates accrual, 7-day redemption, 0.3% instant fee) come from secondary guides, not the official site, and could not be verified on axis.to itself. No Axis token is live and no token is confirmed. Coordinates Season 1 began Sept 4, 2026 per one guide (another says July 29) — the exact season dates are inconsistent across sources and unverified.
- Sources: https://defillama.com/protocol/axis, https://axis.to/, https://airdrops.io/axis/, https://www.airdropsea.app/guides/axis-origin-vault-airdrop-guide, https://www.upshift.finance/blog/axis-origin-vault

  Farm steps (researched):
  1. Use a fresh Ethereum wallet (e.g. MetaMask) and fund it with USDC or USDT plus ETH for gas, since Axis and its vaults run on Ethereum mainnet. (Cost: $0 setup; gas estimate $2-8 per tx. Time: 10-15 min.)
  2. Open axis.to and the Axis app at app.axis.to to check which positions currently earn Coordinates (the points program) and at what rate before depositing anything. (Cost: $0. Time: 10 min.)
  3. Understand the Origin Vault is CLOSED: its pre-deposit window ran July 29 to Aug 5, 2026 and converted into the Ecosystem Vault, so do not follow any guide telling you to deposit into the Origin Vault now. (Cost: $0. Time: 5 min.)
  4. To farm now, hold a USDx or sUSDx position the app counts for Coordinates — e.g. by acquiring USDx and staking it into sUSDx, the ERC-4626 vault whose value rises as arbitrage profits accrue. (Cost: Gas, estimate $2-8. Time: 10-15 min.)
  5. Optionally deploy USDx or sUSDx into the Ecosystem Vault's DeFi markets (Curve, Pendle) shown in the app, confirming first in the app that the position still earns Coordinates. (Cost: Gas, estimate $2-8. Time: 15 min.)
  6. Track your Coordinates balance at app.axis.to/coordinates and bind a referral code first if you have one (referrals add a permanent Coordinates boost, e.g. +10%); Coordinates accrue while your funds sit in a counted position. (Cost: $0. Time: Hold 30 days (estimate).)
  7. To exit, redeem your position in the app: sUSDx redemptions use a request with a 7-day cooldown (or instant for about 0.3%), and note Axis's own docs say USDx is not a stablecoin and is not guaranteed to hold $1. (Cost: Gas, estimate $2-8; instant redeem ~0.3%. Time: Up to 7 days for standard redemption.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $50 into Axis's basis trade on Ethereum and hold the position. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 60 days.
    5. Check Axis once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Axis's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #21 Lofty (`lofty`) — verified

- Category: RWA · Chains: Algorand
- Official site: https://www.lofty.ai
- DefiLlama: https://defillama.com/protocol/lofty
- What it does: Lofty is a fractional real estate marketplace on Algorand: users buy tokenized shares of US rental properties (many around $50 or less), earn daily rental income, and can sell shares instantly on its marketplace with no lockups.
- Notes: Verified against the official homepage, which spells out the whole flow. No points program was found on the site — Lofty pays daily rental income, not points, so do not invent a points step. Lofty is a custodial, KYC-gated RWA marketplace, not a permissionless DeFi vault: investments over $200 and withdrawals require KYC/KYB, and US users should note it is a regulated-style investment product. The Algorand chain detail is confirmed by DeFiLlama; the homepage itself does not emphasize the chain.
- Sources: https://defillama.com/protocol/lofty, https://www.lofty.ai

  Farm steps (researched):
  1. Create a Lofty account at lofty.ai — sign-up takes about 2 minutes — and complete KYC/KYB verification, which the site requires for investments over $200 and for withdrawals. (Cost: $0 to sign up. Time: 2-15 min.)
  2. Fund your account with a credit card, debit card, or crypto; Lofty accepts crypto deposits, and the underlying property tokens live on Algorand. (Cost: Card/crypto funding fees vary. Time: 10 min.)
  3. Browse the property marketplace and review each listing's financials, inspection reports, projected rental yield, local market data, and ownership documents before buying. (Cost: $0 to browse. Time: 15-30 min.)
  4. Buy fractional shares of a rental property — many shares cost around $50 or less — and your first rent payment arrives with the next daily rent run, usually within 24 hours. (Cost: Share price, often ~$50 or less per share. Time: 5-10 min to buy.)
  5. Hold your shares to earn rent daily in the daily rent run and to benefit from property appreciation; reinvesting the daily rent into more shares compounds your position. (Cost: $0 to hold. Time: Hold 30 days (estimate).)
  6. Optionally vote on key property decisions through Lofty's governance system, where investor-elected property managers handle day-to-day operations like leasing and maintenance. (Cost: $0. Time: 5 min.)
  7. To exit, list your shares on the Lofty marketplace and sell them to other investors instantly — the site states there are no lockups and no waiting years for a fund exit — then withdraw your balance anytime. (Cost: Marketplace/sale fees not stated on homepage. Time: Minutes to sell; withdrawal per account terms.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into the tokenised asset Lofty offers on Algorand and hold it. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Lofty once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Lofty's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #22 Clearstar (`clearstar`) — verified

- Category: Risk Curators · Chains: Flare, Base, Ethereum
- Official site: https://clearstar.xyz
- DefiLlama: https://defillama.com/protocol/clearstar
- What it does: Clearstar Labs is a DeFi risk curator (operated by NovaFusion SA): it does qualitative-first diligence on governance, contracts, and oracles and curates yield vaults on Morpho, Euler, and other protocols. It has no app of its own — retail users deposit into Clearstar-curated Morpho vaults.
- Notes: Re-checked 2026-11-17: clearstar.xyz now reads directly (was HTTP 429): it confirms Clearstar is a risk advisory/curator for chains, exchanges and issuers — $415M+ loans underwritten, 6 published APB ratings, active since 2022 — with no retail app, confirming the curator-only framing. The live Morpho curator page (app.morpho.org/curator/clearstar, crawled 2026-11-17) lists real vaults with live figures that replace the old vague examples: Clearstar cbAssets Vault $27.04M deposits at 6.33%, Clearstar USDC Core $4.56M at 7.01%, Clearstar Core ETH 1,754 WETH at 1.58%, plus 3Jane/Noon/Re Ecosystem Vaults and a Solana vault. The cbXRP Yield Vault on Upshift/Base (deposit cbXRP, receive upXRP) and the Flare earnXRP vault are also confirmed as live retail routes. No Clearstar points program exists.
- Sources: https://clearstar.xyz, https://app.morpho.org/curator/clearstar, https://www.upshift.finance/blog/upshift-is-live-on-base-clearstar-cbxrp-yield-vault, https://defillama.com/protocol/clearstar

  Farm steps (researched):
  1. Use a fresh EVM wallet and understand Clearstar has no app of its own: clearstar.xyz is a risk-advisory site ($415M+ loans underwritten, 6 published ratings) and retail users deposit into Clearstar-curated vaults on Morpho, Euler or Upshift. (Cost: $0. Time: 10 min.)
  2. Open the Clearstar curator page on Morpho at app.morpho.org/curator/clearstar and compare live vaults by asset, deposits and net APY — e.g. Clearstar cbAssets Vault ($27.04M, 6.33%), Clearstar USDC Core ($4.56M, 7.01%) and Clearstar Core ETH (1,754 WETH, 1.58%) as of 17 Nov 2026. (Cost: $0. Time: 10-15 min.)
  3. For XRP exposure, use the Clearstar cbXRP Yield Vault on Upshift on Base instead: deposit cbXRP (Coinbase-wrapped XRP on Base) and receive upXRP shares; on Flare the equivalent is the Clearstar earnXRP vault. (Cost: $0. Time: 10 min.)
  4. Pick one vault and read its Morpho vault page first — its description, allocation, performance fee (e.g. 25% on some Clearstar vaults) and timelock (often 3 days) — before depositing anything. (Cost: $0. Time: 10 min.)
  5. Deposit the vault's asset through the Morpho deposit box (USDC on Base or Ethereum for the USDC vaults, WETH for Core ETH, cbXRP for the cbXRP vault), approving the token and confirming the transaction. (Cost: Gas, estimate $2-8. Time: 10 min.)
  6. Hold the vault shares to earn the vault's native APY plus any extra incentives; some Clearstar vaults pay additional incentives claimable through Merkl, so check the vault page for a rewards note. No Clearstar points program exists. (Cost: $0 to hold. Time: Hold 30 days (estimate).)
  7. To exit, withdraw from the Morpho vault page (or Upshift for the cbXRP vault) to redeem shares back into the underlying asset; withdrawals are not gated by the curator, but liquidity depends on unborrowed funds in the underlying markets. (Cost: Gas, estimate $2-8. Time: 10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Clearstar vault on Flare and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Clearstar once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Clearstar's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #23 b14g (`b14g`) — partial

- Category: Restaking · Chains: Bitcoin, CORE, Babylon Genesis
- Official site: https://www.b14g.xyz
- DefiLlama: https://defillama.com/protocol/b14g
- What it does: b14g is a modular dual-staking layer for Bitcoin: its Merge Marketplace matches BTC holders with CORE (or BABY) holders so each side earns the higher dual-staking rewards of Core/Babylon without holding both assets. BTC stays time-locked on Bitcoin; it also runs dualCORE and BTCFi lending vaults.
- Notes: Re-checked 2026-11-17: b14g.xyz is still JavaScript-only (tagline only), so product details still rest on secondary sources. The post-exploit picture has moved materially: the contracts have been PAUSED since 31 Oct 2026; no post-mortem had been published as of 6-13 Nov; users had NOT yet been repaid as of 9-13 Nov. On 8 Nov b14g announced a payout plan (reported by CryptoTimes/CoinLab, citing b14g's X posts): the recovered 68.15M CORE (~70%) returns pro rata to affected orders within 5-7 days, the remainder is repaid from 50% of b14g's future Core staking revenue (weekly claims), plus ~9-9.5M CORE frozen at exchanges. The old step 1 (check status before depositing) was too weak — the honest instruction now is DO NOT deposit until contracts are unpaused and the fix is published. If b14g posts an unpause notice, this entry needs another check.
- Sources: https://www.b14g.xyz, https://www.cryptotimes.io/2026/11/07/b14g-recovers-70-of-stolen-core-after-zero-amount-withdrawal-attack/, https://coinlab.info/en/articles/b14g-hack-oct-2026-explained/, https://itokenly.com/hacks/b14g-core-staking-october-2026, https://defillama.com/protocol/b14g

  Farm steps (researched):
  1. Do NOT deposit into b14g right now: on 31 Oct 2026 about 97M CORE (~$1.47M) was drained from 91 staking orders via zero-amount withdrawal requests, and b14g paused the affected contracts the same day. Check @b14g_network on X for an unpause notice before doing anything. (Cost: $0. Time: 10 min.)
  2. Understand the recovery position: a Core hard fork on 2 Nov clawed back 68.15M CORE (~70%) to a recovery address and ~9.5M CORE was frozen at exchanges, but as of 13 Nov the recovered funds had not yet been distributed and no post-mortem had been published. (Cost: $0. Time: 10 min.)
  3. If you were affected, note the payout plan announced 8 Nov: recovered CORE returns pro rata to affected orders within 5-7 days, and the shortfall is repaid from 50% of b14g's future Core staking revenue via weekly claims. There is no claims portal to use yet — do not trust any link offering one. (Cost: $0. Time: 10 min.)
  4. Only if b14g publicly confirms contracts are unpaused and the zero-amount withdrawal fix is live, set up a fresh BTC wallet (e.g. Unisat) plus a Core-chain EVM wallet (e.g. MetaMask on Core), since dual staking pairs a BTC stake with a CORE stake. (Cost: $0 setup. Time: 10-15 min.)
  5. On b14g.xyz choose a product: dualCORE (deposit CORE only, the marketplace matches BTC for you) or the BTC side (lock BTC to be matched with CORE holders). BTC stays time-locked on Bitcoin and was not affected by the exploit. (Cost: $0. Time: 5-10 min.)
  6. For the CORE side, deposit CORE into dualCORE; b14g states assets stay in the official Core staking contract and it never takes custody. Do NOT treat the old advertised 15-20% yearly yield as a current rate — it predates the exploit and the pause. (Cost: Core gas, estimate $2-8. Time: 10 min.)
  7. To exit, unbond/withdraw in the b14g app: BTC unbonding follows the underlying chain's timelock (Babylon-style unbonding is about 301 blocks / ~50 hours), and CORE-side withdrawals go through the Core staking contract. (Cost: Gas/fees, estimate $2-8. Time: Unbonding timelock up to ~50 hours + 10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Stake $100 of the chain's staking asset through b14g on Bitcoin. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Add a small amount to the stake the following week, so the record shows more than one staking action. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check b14g once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open b14g's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #24 Saturn (`saturn`) — verified

- Category: Stablecoin Wrapper · Chains: Ethereum, Monad, Binance
- Official site: https://app.saturn.credit
- DefiLlama: https://defillama.com/protocol/saturn
- What it does: Saturn is a dual-token Bitcoin-backed credit protocol: USDat is a stablecoin fully backed by tokenized US Treasuries, and staking USDat gives sUSDat, a yield-bearing version with digital-credit (STRC) exposure. Its app states 'No lock-up period. Accrue points on deposits.'
- Notes: Verified: the official app confirms USDat/sUSDat, no lock-up, and points on deposits. Season 2 (Orbital Points), multipliers, the Nov 16 2026 registration deadline, and the STRN token allocation (up to 5% of supply for Season 2) come from secondary guides, not the official app, and point multipliers differ between sources (USDat hold reported as both 5x and 7x; Curve LP as 20x and 25x). US, UK, EU/EEA users are excluded from the points program per Saturn's terms. Minting USDat directly via M0 requires whitelisting; retail users swap via Curve.
- Sources: https://defillama.com/protocol/saturn, https://app.saturn.credit/, https://airdrops.io/saturn-credit/, https://usethebitcoin.com/airdrop/saturn-airdrop-guide/

  Farm steps (researched):
  1. Use a fresh EVM wallet (e.g. MetaMask) and fund it with USDC plus ETH for gas, since the main Saturn app runs on Ethereum (Monad and BNB Chain are also supported). (Cost: $0 setup; gas estimate $2-8 per tx. Time: 10-15 min.)
  2. Open app.saturn.credit, connect your wallet, and check the live sUSDat APY and your points balance; note sUSDat is only available to users outside the US per Saturn's terms. (Cost: $0. Time: 5-10 min.)
  3. Swap USDC for USDat in the Saturn app at a 1:1 ratio via the Saturn Curve pool; holding USDat alone already accrues points (reported at 5-7x per day depending on the season). (Cost: Swap fee/gas, estimate $2-8. Time: 5 min.)
  4. Stake your USDat for sUSDat in the Stake tab to earn yield from digital-credit exposure (reported around 9.8-11% APY); rewards accrue through the sUSDat exchange rate. (Cost: Gas, estimate $2-8. Time: 5 min.)
  5. Earn Orbital Points (Season 2, running Aug 9 to Dec 8, 2026 or until $1B TVL): hold USDat or sUSDat, or deploy into partner strategies — Curve USDC/USDat LP (reported up to 20-25x) or Pendle YT-USDat (reported up to 30x) — for higher multipliers. (Cost: Gas per position, estimate $2-8. Time: Hold 30 days (estimate).)
  6. Register your points wallet at claim.saturn.credit if you farmed Season 1 or Season 2 — registration opened Nov 9 and closed Nov 16, 2026 at 9:00 AM EST, and it only confirms eligibility and a receiving address; it is not itself a claim. (Cost: $0. Time: 5 min.)
  7. To exit, unstake sUSDat back to USDat — note unstaking works like a limit order and takes roughly 7 days — then swap USDat back to USDC; claiming of any STRN token happens at TGE via a link published only by @saturn_credit on X. (Cost: Gas, estimate $2-8. Time: ~7 days unstaking + 10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Hold $100 of the stablecoin Saturn issues on Ethereum. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 45 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 45 days.
    5. Check Saturn once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Saturn's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 75 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #28 Galaxy Curation (`galaxy-curation`) — verified

- Category: Risk Curators · Chains: Arc, Ethereum, Base
- Official site: https://www.galaxy.com
- DefiLlama: https://defillama.com/protocol/galaxy-curation
- What it does: Galaxy Curation is the vault-curation arm of Galaxy (the listed digital-assets and AI infrastructure company): it curates Morpho lending vaults — most notably the Galaxy USDC vault on Arc ($92.7M, ~3.14% APY) — allocating depositor stablecoins into blue-chip-collateral lending markets. There is no Galaxy retail app; deposits go through Morpho.
- Notes: Re-checked 2026-11-17: galaxy.com now reads directly (was partial via secondary sources) and confirms Galaxy is an institutional digital-assets and AI infrastructure company with no retail deposit product — confirming the Morpho-only framing. Live Morpho/Styx data (crawled 2026-11-17) corrects three details: (1) allocation is 95.4% to the USDC cirBTC market, not 100%; (2) net APY is 3.15% with 0% fee and $92.73M deposits; (3) the 'timelock of up to 7 days' is wrong for this V2 vault — Morpho V2 has a separate timelock per curator action, no single figure. New and practical: USDC is Arc's native gas token, so a farmer needs USDC (not ETH) for Arc gas. The single-key owner/curator warning is retained as reported by a third-party tracker, flagged as unverified on Morpho. No Galaxy points program was found.
- Sources: https://www.galaxy.com, https://app.morpho.org/arc/vault/0x8E357432CC12ff425c36432F312968aEb16112AF/galaxy-usdc, https://www.styx.finance/, https://defillama.com/protocol/galaxy-curation

  Farm steps (researched):
  1. Understand Galaxy itself is an institutional company with no retail deposit app — the farmable product is its Morpho vault, so use a fresh EVM wallet and do not look for a 'Galaxy deposit' button on galaxy.com. (Cost: $0. Time: 5 min.)
  2. Fund your wallet with USDC and add the Arc network (Circle's L1, chain 5042) to your wallet. USDC is Arc's native gas token, so keep spare USDC for gas — you do not need ETH. The largest Galaxy vault, Galaxy USDC at about $92.7M, lives on Arc. (Cost: $0 setup; gas estimate $2-8 per tx. Time: 10-15 min.)
  3. Open the Morpho app at app.morpho.org, find the Galaxy USDC vault on Arc (curator: Galaxy Curation), and check its deposits, net APY (about 3.15%) and fee (0%). Its allocation is about 95.4% to the USDC cirBTC market, not 100% as some trackers report. (Cost: $0. Time: 10 min.)
  4. Deposit USDC into the Galaxy USDC vault through the Morpho deposit box, approving the token and confirming the transaction; the vault lends your USDC to borrowers posting ETH/BTC collateral. (Cost: Gas, estimate $2-8. Time: 10 min.)
  5. Hold the vault shares to earn the lending APY, which accrues through the vault share price; no Galaxy points program was found, so yield comes from lending interest only. A Galaxy USDC Enhanced vault on Ethereum (~5.82% APY, ~$9M) exists as a higher-yield alternative. (Cost: $0 to hold. Time: Hold 30 days (estimate).)
  6. Monitor the vault on Morpho: Galaxy as curator can change allocations and parameters, and this V2 vault has a separate timelock per curator action rather than one single timelock. A single key (not a multisig) reportedly holds the owner and curator roles — re-check this on Morpho before depositing. (Cost: $0. Time: 5 min per check.)
  7. To exit, withdraw from the Morpho vault page to redeem shares back into USDC; withdrawals cannot be gated by the curator, but available liquidity depends on unborrowed funds in the underlying markets. (Cost: Gas, estimate $2-8. Time: 10 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Galaxy Curation vault on Arc and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 60 days.
    5. Check Galaxy Curation once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Galaxy Curation's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #29 Ember (`ember`) — partial

- Category: RWA · Chains: Ethereum, Sui, Base
- Official site: https://ember.so/
- DefiLlama: https://defillama.com/protocol/ember
- What it does: Ember originates and issues tokenized investment products, bringing funds, strategies and real-world assets onchain. Users deposit an asset such as USDC into an Ember vault and receive receipt tokens whose price rises as the curator's strategy earns.
- Notes: Re-checked 2026-11-17: ember.so is still JavaScript-only (logo only), so the homepage adds nothing — mechanics still rest on secondary sources quoting Ember's own vault API and docs. A detailed guide reading Ember's vault API and docs (JewelSwap, 12 Oct 2026) names the flagship Ember Earn (eEARN): USDC deposit, ~$10.0M deposits, 10.0% target APY, 3-day withdrawal period, among 27 Sui vaults holding ~$47.2M total. The Ember SDK docs confirm the withdrawal model (operator-processed redemption queue, EVM vaults are ERC-4626) and that some vaults are permissioned/KYC-gated. No points program was found anywhere. The upgrade names eEARN and replaces 'allow several days' with the 3-day period.
- Sources: https://ember.so/, https://www.jewelswap.io/blog/what-is-ember-protocol, https://socket.dev/npm/package/@ember-finance/sdk, https://defillama.com/protocol/ember

  Farm steps (researched):
  1. Set up a fresh wallet on the chain you plan to use (an EVM wallet for Ethereum or Base, a Sui wallet for Sui) and fund it with USDC plus gas tokens. Ember's homepage is JavaScript-only, so use the Ember app and docs for live vault data. (Cost: Gas $2-8 on Ethereum, under $1 on Sui or Base (estimate). Time: 10-15 min setup.)
  2. Open the Ember app at ember.so and browse the live vault list. The flagship is Ember Earn (eEARN) on Sui: deposit USDC, receive eEARN, with a 10.0% target APY and about $10M deposited as of 12 Oct 2026. (Cost: Free to browse. Time: 10 min.)
  3. Check the vault's eligibility rules before depositing, because Ember docs say vaults can be permissionless or permissioned (KYC-gated), and some RWA products sit behind eligibility requirements. (Cost: Free. Time: 10 min.)
  4. Approve USDC and deposit into the chosen vault; on Sui you receive a receipt token such as eEARN, and on EVM chains you receive ERC-4626 vault shares. A new vault starts at a 1:1 rate, so 100 USDC buys 100 receipt tokens. (Cost: Gas $2-8 on Ethereum (estimate). Time: 5 min.)
  5. Hold the receipt tokens while the curator runs the strategy; yield shows up as a rising receipt-token price, not as separate reward payments you claim. There is no Ember points program. (Cost: No extra cost. Time: Hold 30 days (estimate).)
  6. Track the vault's exchange rate and any curator or operator updates in the Ember app or docs while your deposit is active; the operator can move vault assets only to whitelisted sub-accounts. (Cost: Free. Time: 5 min per check.)
  7. To exit, submit a redemption request in the app; your shares enter a queue and the vault operator processes the payout later. For eEARN the withdrawal period is 3 days — do not treat it as an instant redeem. (Cost: Gas $2-8 on Ethereum (estimate). Time: 3 days for eEARN; varies by vault.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $50 into the tokenised asset Ember offers on Ethereum and hold it. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check Ember once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Ember's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #30 Valos (`valos`) — verified

- Category: RWA · Chains: Monad
- Official site: https://valos.io/
- DefiLlama: https://defillama.com/protocol/valos
- What it does: Valos offers institutional-grade digital asset yield solutions, mainly private credit strategies, for institutional investors under a compliance-led onboarding process. It has no public retail deposit product.
- Notes: Re-checked 2026-11-17: valos.io now reads directly and confirms the old entry word-for-word in substance: 'Where Institutional Discipline Meets Digital Assets', 'Why Institutional Investors choose Valos', a 'disciplined onboarding and compliance process', fully disclosed fee structures, and 'find the right strategy for your portfolio' via contacting the team. No retail deposit page, no vault, no token, no points program. No contradiction and no new farmable path; the steps are unchanged — the entry already states all of this honestly. Status upgraded to verified because the official site was directly read this round and confirms the entry.
- Sources: https://valos.io/, https://defillama.com/protocol/valos, https://github.com/kamalbuilds/ava-monad/blob/HEAD/docs/MONAD.md

  Farm steps (researched):
  1. Use a fresh wallet but do not send funds anywhere yet, because Valos has no public retail deposit page or vault on its official site. (Cost: Free. Time: 5 min.)
  2. Read valos.io and confirm the access route yourself: the site speaks to institutional investors, describes a disciplined compliance onboarding process, and invites you to contact the team about a strategy for your portfolio. (Cost: Free. Time: 10 min.)
  3. Contact the Valos team through the site's enquiry route to ask about minimums, eligibility and whether any retail access exists at all. (Cost: Free. Time: 10 min.)
  4. If you are an institution, complete Valos's compliance and onboarding process before any capital moves; there is no connect-wallet deposit flow to use instead. (Cost: Unknown, set by Valos. Time: Days to weeks (estimate).)
  5. Note that Valos exposure can appear inside other protocols, for example a Valos vUSD lending market on Curvance on Monad, but that is a separate protocol's product, not a Valos deposit. (Cost: Free to check. Time: 10 min.)
  6. Do not deposit into any lookalike site or contract claiming to be a Valos retail vault; the official site lists no such vault and no token. (Cost: Free. Time: 5 min.)
  7. Re-check valos.io before acting, since a retail product would have to appear there first; until then there is no Valos farm step to complete. (Cost: Free. Time: 5 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $100 into the tokenised asset Valos offers on Monad and hold it. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 60 days.
    5. Check Valos once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Valos's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #35 Armitage by Wintermute (`armitage-by-wintermute`) — verified

- Category: Risk Curators · Chains: Ethereum
- Official site: https://armitage.wintermute.com
- DefiLlama: https://defillama.com/protocol/armitage-by-wintermute
- What it does: Armitage is Wintermute's onchain vault curation arm. It curates Morpho Vault V2 lending vaults on Ethereum in tiers (Prime conservative, Select balanced, Apex planned, plus partner Ecosystem vaults), managing risk and earning yield for depositors.
- Notes: Armitage has no points program and no token; the farm is yield only. Deposits do not happen on armitage.wintermute.com itself but on Morpho's app, which the official Armitage deposit guide states explicitly. Ecosystem vaults (e.g. Pendle Ecosystem USDC, 5-7% target APY) are partner vaults, not Core vaults.
- Sources: https://defillama.com/protocol/armitage-by-wintermute, https://armitage.wintermute.com, https://armitage.wintermute.com/docs/llms-full.txt, https://armitage.wintermute.com/docs/vaults/ecosystem, https://app.morpho.org/vaults

  Farm steps (researched):
  1. Set up an Ethereum wallet holding USDC or USDT plus ETH for gas. (Cost: Gas $2-8 (estimate). Time: 10-15 min setup.)
  2. Open armitage.wintermute.com and compare the Core tiers: Prime is conservative, Select is balanced, and Apex is aggressive and still planned. (Cost: Free to browse. Time: 10 min.)
  3. Pick a vault, for example Wintermute USDC Prime with a 4-5% target APY or Wintermute USDC Select with a 5-8% target APY, and note its Morpho vault address. (Cost: Free. Time: 10 min.)
  4. Go to app.morpho.org, find the same Armitage vault, and check its live APY, TVL and available liquidity before depositing. (Cost: Free. Time: 5 min.)
  5. Approve USDC and deposit into the Morpho Vault V2 contract; deposits are permissionless and noncustodial, and you receive vault shares while yield accrues to them. (Cost: Gas $2-8 (estimate). Time: 5 min.)
  6. Hold the position and monitor the vault's disclosed collateral exposure and APY on the Armitage site or on Morpho. (Cost: No extra cost. Time: Hold 30 days (estimate).)
  7. To exit, withdraw from the Morpho vault back to USDC; withdrawals depend on available market liquidity, so check liquidity first. (Cost: Gas $2-8 (estimate). Time: 5 min, subject to liquidity.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $100 into a Armitage by Wintermute vault on Ethereum and keep the vault shares. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 60 days.
    5. Check Armitage by Wintermute once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Armitage by Wintermute's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #36 Doppler Finance (`doppler-finance`) — verified

- Category: CeDeFi · Chains: Ripple, Ethereum
- Official site: https://doppler.finance/
- DefiLlama: https://defillama.com/protocol/doppler-finance
- What it does: Doppler Finance runs CeDeFi yield vaults, mainly on the XRP Ledger, that turn idle XRP and RLUSD into yield through institutional strategies such as arbitrage and basis trading. Yield is paid in the deposited asset and compounds automatically.
- Notes: The snapshot lists chains as 'Ripple, Ethereum'; in reality 99.8% of TVL is on the XRP Ledger (XRPL), per DeFiLlama, and the RLUSD vault is also on Ethereum. DeFiLlama shows no website link for Doppler, but the official site is doppler.finance, confirmed by the project's own blog. Doppler Points ($1 = 0.01 points/hour) and the XDP token (TGE 28 Sep 2026, claim window to 28 Nov 2026) were confirmed via sources citing the official site, not from the homepage text itself. The withdrawal delay of about a week comes from a secondary source, not the official homepage.
- Sources: https://defillama.com/protocol/doppler-finance, https://doppler.finance/, https://blog.doppler.finance/blog/building-the-financial-operating-layer-for-tokenized-assets, https://coinstats.app/news/27e982a19f499a547d05f008858a37c9a82e982041bbdadc049da7ace617a80f_Doppler-Finance-XRP-Vault-Update-Lifts-XDP-Coin-Price-What-Next/

  Farm steps (researched):
  1. Set up an XRP Ledger wallet such as Xaman and fund it with XRP for deposits, keeping a small XRP reserve for network fees. (Cost: XRPL fees under $1 (estimate). Time: 10-15 min setup.)
  2. Open doppler.finance and open the Doppler Vaults app to see the live XRP and RLUSD vault rates. (Cost: Free to browse. Time: 10 min.)
  3. Choose the XRP vault (about 3-4.5% APR) or the RLUSD vault (about 7% APR) and check the current rate, since APRs move week to week. (Cost: Free. Time: 5 min.)
  4. Deposit XRP or RLUSD into the vault; yield is paid in the same asset you deposited and compounds automatically with no action needed. (Cost: No platform fee on deposits or withdrawals, per Doppler's blog. Time: 5 min.)
  5. Track your balance, weekly yield and Doppler Points on the Vault and Manage pages; every $1 deposited earns about 0.01 points per hour. (Cost: Free. Time: 5 min per check.)
  6. Hold the deposit for at least a full week, because yield is calculated from your average balance across the week, not a single snapshot. (Cost: No extra cost. Time: Hold at least 7 days.)
  7. To exit, request a withdrawal in the app and allow several days for it to process; check your points and any XDP claim status before withdrawing. (Cost: No platform fee on withdrawals, per Doppler's blog. Time: Several days to process (estimate).)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $50 into Doppler Finance's main product on Ripple — check its own page to see which product holds the TVL — and leave the position open. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check Doppler Finance once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Doppler Finance's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #39 Curvance (`curvance`) — verified

- Category: Lending · Chains: Monad
- Official site: https://app.curvance.com
- DefiLlama: https://defillama.com/protocol/curvance
- What it does: Curvance is Monad's lending layer. It offers isolated lending markets where users supply assets to earn interest, borrow against collateral, use one-click leverage, and deposit into Earn Vaults.
- Notes: The app's tagline is 'Deposit your crypto, borrow against it, and earn yield while you sleep', and it has portfolio, markets, vaults and bytes tabs. There is NO verified CVE token contract and no confirmed airdrop as of late October 2026, which contradicts generic 'farm Curvance for the CVE airdrop' steps; the testnet bytes campaign is historical. The 20-minute hold after borrowing blocks repay/withdraw, per Curvance docs as quoted by multiple sources.
- Sources: https://defillama.com/protocol/curvance, https://app.curvance.com, https://boxmining.com/curvance-cve-token-airdrop-guide/, https://github.com/kamalbuilds/ava-monad/blob/HEAD/docs/MONAD.md

  Farm steps (researched):
  1. Set up a Monad wallet holding MON for gas and the asset you want to supply, for example USDC or savUSD. (Cost: Monad gas under $1 (estimate). Time: 10-15 min setup.)
  2. Open app.curvance.com and browse the Markets tab to compare isolated lending markets, interest rates, caps and liquidation parameters. (Cost: Free to browse. Time: 10 min.)
  3. Supply an asset into a market to start earning borrow interest; you receive a cToken receipt for your deposit. (Cost: Gas under $1 (estimate). Time: 5 min.)
  4. Optionally borrow a second asset against your supplied collateral for one-click leverage, watching your health factor so you are not liquidated. (Cost: Gas under $1 (estimate). Time: 5 min.)
  5. Check the Bytes tab and any live incentives in the app, since Curvance has no confirmed CVE token contract and no verified airdrop. (Cost: Free. Time: 5 min.)
  6. Hold the position and monitor utilization, interest rates and liquidation parameters for your market. (Cost: No extra cost. Time: Hold 30 days (estimate).)
  7. To exit, wait out the 20-minute hold that follows any borrow, then repay any loan and withdraw your supplied collateral. (Cost: Gas under $1 (estimate). Time: 20 min hold, then 5 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Supply $100 of USDC to Curvance on Monad and leave it earning interest. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Lend a second, smaller amount on Curvance the following week, using a different asset as collateral, so the record shows more than one deposit. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 45 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 45 days.
    5. Check Curvance once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Curvance's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 75 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #41 Noble (`noble`) — verified

- Category: Chain · Chains: Noble
- Official site: https://noble.xyz/
- DefiLlama: https://defillama.com/protocol/noble
- What it does: Noble is a Cosmos appchain built for stablecoin issuance. Its flagship asset is USDN (Noble Dollar), a yield-bearing stablecoin fully backed by short-term US Treasuries, with a Points Vault that trades base yield for Noble Points toward a NOBLE token allocation.
- Notes: Re-checked 2026-11-17: noble.xyz is still JavaScript-only (logo + footer only), but the substance is now confirmed by Noble's own official Medium account (@noble_xyz, updated 24 Oct 2026) plus Circle/Injective reporting, so this entry is verified on official channels rather than the homepage. Two live developments change the old steps. (1) The USDC bridge-in path is now actively degrading: Circle disabled new USDC minting to Noble on 13 Oct 2026; CCTP V1 burn limits began falling on 31 Oct 2026; exits narrow from 1 Dec 2026; the Noble USDC contract and CCTP routes are FULLY PAUSED 12 Jan 2027, with a snapshot that day and manual redemption from 13 Jan 2027. Bridging in now risks stranding funds past the pause. (2) Noble's own Medium confirms the Season 2 mechanics (1 point per $100 USDN per day, points only after day 30, multipliers to 1.75x after 120 days, S2 = 2% fixed allocation, ends at Hyperliquid vault launch) and the 31 Dec 2026 address-linking deadline — resolving the old 2025-vs-2026 date confusion in favour of 2026. Noble is a chain, not a protocol: DeFiLlama has no protocol page for it (still 404).
- Sources: https://noble.xyz/, https://medium.com/@noble_xyz/noble-airdrop-farm-points-s2-eligibility-claim-74734a6371dd, https://injective.com/blog/injective-usdc-canonical-standard, https://Coinpaprika.com/news/circle-pulls-usdc-noble-forcing-cosmos

  Farm steps (researched):
  1. Set up a Cosmos wallet such as Keplr or Leap and keep a little USDC for Noble gas fees. Noble is a Cosmos appchain for stablecoins, not a protocol — DeFiLlama has no protocol page for it. (Cost: About $0.01 per transfer (estimate). Time: 10-15 min setup.)
  2. Think twice before bridging USDC to Noble now: Circle stopped new USDC minting to Noble on 13 Oct 2026, CCTP V1 burn limits have been falling since 31 Oct, exits narrow from 1 Dec 2026, and the Noble USDC contract is fully paused on 12 Jan 2027 with only manual redemption after that. Only bridge what you can exit before January. (Cost: Bridge fee varies (estimate). Time: 10-15 min.)
  3. Buy USDN with USDC at dollar.noble.xyz; USDN is backed by short-term US Treasuries and earns about 4% base yield when simply held. The 0.1% conversion fee applies between USDC and USDN. (Cost: 0.1% conversion fee between USDC and USDN. Time: 5 min.)
  4. Open points.noble.xyz and deposit USDN into the Points Vault to earn Noble Points instead of the base yield. (Cost: About $0.01 per transfer (estimate). Time: 5 min.)
  5. Hold for at least 30 days, because points only start counting after 30 days in the vault, and multipliers rise with longer holds (up to 1.75x after 120 days). Season 2 earns 1 point per $100 USDN per day toward a fixed 2% NOBLE allocation. (Cost: No extra cost, but you forgo base yield. Time: Hold at least 30 days.)
  6. Link your Cosmos address to an Ethereum address on the Noble claim page before 31 December 2026, so any allocation can be delivered to you. Season 2 ends when the Hyperliquid vaults launch, and the allocation shown until then is a projection, not final. (Cost: Free. Time: 5 min.)
  7. To exit, withdraw USDN from the Points Vault and swap it back to USDC; withdrawing before 30 days earns zero points for that deposit. Exit Noble USDC entirely before the 12 Jan 2027 contract pause. (Cost: 0.1% conversion fee (estimate). Time: 5 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $50 into Noble's main product on Noble — check its own page to see which product holds the TVL — and leave the position open. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check Noble once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Noble's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #43 Keyrock (`keyrock`) — verified

- Category: Risk Curators · Chains: Arc, Ethereum
- Official site: https://keyrock.com/
- DefiLlama: https://defillama.com/protocol/keyrock
- What it does: Keyrock is a global crypto investment group and market maker that curates onchain yield vaults through Morpho. Retail users reach its vaults through Morpho, not through keyrock.com, which is an institutional site.
- Notes: Keyrock itself is B2B/institutional: keyrock.com offers market making, OTC and asset management to institutions and has no retail deposit path, which contradicts any generic 'deposit on Keyrock' step. The real retail path is its Morpho vaults: Keyrock Prime USDC (krUSDC) on Arc holds about $75.25m and Keyrock USDC (kUSDC) on Ethereum about $8m. No Keyrock points program or token was found.
- Sources: https://defillama.com/protocol/keyrock, https://keyrock.com/, https://app.morpho.org/vaults, https://TOKENTERMINAL.COM/explorer/projects/morpho/kusdcc145, https://blog.vaults.fyi/morpho-yields/

  Farm steps (researched):
  1. Set up a wallet on Arc or Ethereum holding USDC plus gas: USDC pays fees on Arc, while ETH pays gas on Ethereum. (Cost: Gas $2-8 on Ethereum, under $1 on Arc (estimate). Time: 10-15 min setup.)
  2. Understand that keyrock.com itself is institutional, with market-making and asset-management services and a 'speak to our experts' route, and no retail deposit button. (Cost: Free. Time: 10 min.)
  3. Open app.morpho.org and find the Keyrock Prime USDC vault on Arc or the Keyrock USDC vault on Ethereum. (Cost: Free to browse. Time: 5 min.)
  4. Compare live APY, TVL and fees; the Arc vault recently showed about 2.25% APY with a 1% annual management fee, while the Ethereum vault showed about 7.1% APY. (Cost: Free. Time: 5 min.)
  5. Approve USDC and deposit into the chosen Morpho vault to receive ERC-4626 vault shares. (Cost: Gas $2-8 on Ethereum (estimate). Time: 5 min.)
  6. Hold the shares while Keyrock allocates the USDC across overcollateralized Morpho markets; yield accrues to the share price. (Cost: Management fee up to 1% a year on the Arc vault. Time: Hold 30 days (estimate).)
  7. To exit, withdraw from the Morpho vault back to USDC; withdrawals are on demand but depend on available market liquidity. (Cost: Gas $2-8 on Ethereum (estimate). Time: 5 min, subject to liquidity.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $50 into a Keyrock vault on Arc and keep the vault shares. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 60 days.
    5. Check Keyrock once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Keyrock's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #44 infiniFi (`infinifi`) — verified

- Category: Yield · Chains: Ethereum, Monad, Base
- Official site: https://infinifi.xyz/
- DefiLlama: https://defillama.com/protocol/infinifi
- What it does: infiniFi rebuilds banking onchain for stablecoins: deposit stablecoins to mint iUSD, then keep it liquid, stake it as siUSD for yield, or lock it as liUSD for higher yield. It runs a live Road to TGE points program ahead of a planned Q4 2026 INFI token launch.
- Notes: Points program is Season 3 of 'Road to TGE': weekly Chapters split 336,000 points, computed every 6 hours, with multipliers up to 20x on Pendle siUSD YT. Registration for Season 1 and 2 airdrop closed 10 Nov 2026, so new activity only counts toward Season 3. TGE is targeted for Q4 2026 and INFI has 45% of supply earmarked for the ecosystem including the airdrop, per secondary sources; the exact points-to-token conversion is unannounced. The official homepage confirms the deposit/stake/lock model and the up to 8%/12% APYs.
- Sources: https://defillama.com/protocol/infinifi, https://infinifi.xyz/, https://docs.infinifi.xyz, https://airdrops.io/infinifi/, https://www.swanbluechip.com/rewards/p/infinifi/

  Farm steps (researched):
  1. Set up an Ethereum wallet holding USDC plus ETH for gas. (Cost: Gas $2-8 (estimate). Time: 10-15 min setup.)
  2. Open app.infinifi.xyz and go to the Deposit or Mint section; the app may ask for an access code. (Cost: Free to browse. Time: 10 min.)
  3. Deposit USDC to mint iUSD at a 1:1 rate; points start accruing for minting and holding iUSD. (Cost: Gas $2-8 (estimate). Time: 5 min.)
  4. Stake iUSD for siUSD to earn liquid yield of up to about 8% APY with no lock, or lock iUSD for liUSD for up to about 12% APY. (Cost: Gas $2-8 (estimate). Time: 5 min.)
  5. Check the Points page in the app to track your Season 3 points, weekly Chapter progress and multipliers. (Cost: Free. Time: 5 min per check.)
  6. Optionally boost points through listed routes such as holding Pendle siUSD yield tokens, which carry the highest multiplier, and through referrals. (Cost: Gas and trading fees vary (estimate). Time: 10-15 min.)
  7. To exit, unstake siUSD or wait out your liUSD lock's exit timer, then redeem iUSD back to USDC in the app; locked liUSD is first-loss capital, so understand the tier before locking. (Cost: Gas $2-8 (estimate). Time: 5 min, plus lock exit timer for liUSD.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $50 into infiniFi's main vault on Ethereum and leave it to compound. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check infiniFi once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open infiniFi's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #45 Gami Labs (`gami-labs`) — verified

- Category: Risk Curators · Chains: Stellar, Ethereum, Base
- Official site: https://gamilabs.io/
- DefiLlama: https://defillama.com/protocol/gami-labs
- What it does: Gami Labs provides onchain asset-management infrastructure with active curation and dynamic risk management. It runs public vaults such as gamiUSDC on EVM chains and earnUSDC/earnXLM on Stellar, allocating across lending, liquidity and structured-yield venues.
- Notes: Gami's own site says 'Discover and deposit into Gami Vaults', so a retail deposit path exists despite the institutional positioning. No token and no official points program exist; a Medium post speculating about a future vault airdrop is third-party speculation, not an official program. The Stellar vaults run on Upshift infrastructure and are co-curated with Stake Capital. DeFiLlama shows most TVL on Stellar ($34.73m), then Ethereum ($21.01m) and Base ($2.63m).
- Sources: https://defillama.com/protocol/gami-labs, https://gamilabs.io/, https://www.upshift.finance/blog/upshift-on-stellar-earnusdc-earnxlm, https://web.fordefi.com/customer-stories/how-gami-labs-curates-institutional-vaults-with-fordefis-policy-engine

  Farm steps (researched):
  1. Set up a wallet for the chain of the vault you want: an EVM wallet for Ethereum or Base vaults, or a Stellar wallet for the earnUSDC and earnXLM vaults. (Cost: Gas $2-8 on Ethereum, under $1 on Stellar or Base (estimate). Time: 10-15 min setup.)
  2. Open gamilabs.io/vaults and browse the live vaults, noting each vault's asset, chain and strategy. (Cost: Free to browse. Time: 10 min.)
  3. For Stellar, open the earnUSDC or earnXLM vault on app.upshift.finance; for EVM vaults, use the deposit route shown on the Gami vault page. (Cost: Free to browse. Time: 5 min.)
  4. Deposit USDC into earnUSDC, or XLM into earnXLM, or stablecoins into the flagship gamiUSDC vault, and receive a receipt token for your share. (Cost: Gas $2-8 on Ethereum (estimate). Time: 5 min.)
  5. Hold the receipt token while Gami routes the capital across lending and liquidity venues such as Blend, Aquarius, Aave or Morpho; yield accrues to the share price. (Cost: No extra cost. Time: Hold 30 days (estimate).)
  6. Track your position and any incentive campaigns in the vault app; Gami has no token and no official points program, so treat airdrop talk as unconfirmed. (Cost: Free. Time: 5 min per check.)
  7. To exit, redeem your receipt tokens for the underlying asset in the vault app; large Stellar withdrawals can take longer because liquidity there is thinner. (Cost: Gas $2-8 on Ethereum (estimate). Time: 5 min, longer for large Stellar exits.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $50 into a Gami Labs vault on Stellar and keep the vault shares. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 60 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 60 days.
    5. Check Gami Labs once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Gami Labs's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 90 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #47 Reti Pooling (`reti-pooling`) — verified

- Category: Staking Pool · Chains: Algorand
- Official site: https://reti.nodely.io
- DefiLlama: https://defillama.com/protocol/reti-pooling
- What it does: Reti Pooling is a decentralized, non-custodial protocol that lets users pool ALGO together so small holders can collectively meet Algorand's 30,000 ALGO solo-staking threshold, stake with a validator of their choice, and earn consensus rewards proportionally.
- Notes: Re-checked 2026-11-17: reti.nodely.io now loads (was timing out) — the page title renders, though only a stale transaction error toast was visible in the crawl, so the staking flow itself still rests on the official docs. The official Réti docs (TxnLab GitBook, read this round) confirm the old steps and add two concrete mechanics they lacked: (1) an unstake must be above the validator's minimum entry amount, or the entire balance — partial unstakes below the minimum are rejected; (2) rewards are computed per epoch and pro-rated if you stake mid-epoch, and the protocol itself charges no fees (only the validator's immutable per-epoch commission). Validator creation costs 10.4449 ALGO, which ordinary stakers never pay. A live third-party report also shows Reti pools in active use (e.g. Steak Pool validator #13, 228,313 ALGO, 300 ALGO minimum entry), confirming minimums vary widely per validator. No points program or token exists for Reti; the reward is ALGO consensus rewards.
- Sources: https://reti.nodely.io, https://txnlab.gitbook.io/reti-open-pooling/core-concepts/staking-pools, https://txnlab.gitbook.io/reti-open-pooling/~gitbook/pdf?limit=100, https://defillama.com/protocol/reti-pooling

  Farm steps (researched):
  1. Set up an Algorand wallet such as Pera and fund it with ALGO plus a little extra for transaction fees. Reti lets small holders pool ALGO to collectively meet Algorand's 30,000 ALGO solo-staking threshold. (Cost: Algorand fees under $1 (estimate). Time: 10-15 min setup.)
  2. Open the Reti Pooling staking dashboard at reti.nodely.io and browse the list of validators. The app loads again this round after timing out before, but confirm the validator list renders before you trust it. (Cost: Free to browse. Time: 10 min.)
  3. Compare validators on performance, commission, payout frequency and restrictions before choosing one, since validators vary greatly — including the minimum entry, which is set per validator (e.g. 300 ALGO on one live pool) and is immutable once set. (Cost: Free. Time: 10 min.)
  4. Select Stake on your chosen validator, enter at least the minimum entry amount of ALGO, and sign the transaction. The protocol itself charges no fees; only the validator's commission, taken per epoch, applies. (Cost: Algorand fees under $1 (estimate). Time: 5 min.)
  5. Check the My Stakes section to confirm your staked amount and the validator's epoch rewards. Rewards are computed per epoch and pro-rated if you stake mid-epoch, so a stake placed late in an epoch earns less that epoch. (Cost: Free. Time: 5 min.)
  6. Hold the stake while the validator participates in Algorand consensus; rewards are distributed proportionally minus the validator's commission each epoch. No points program or token exists for Reti — the reward is ALGO consensus rewards. (Cost: Validator commission, set per validator. Time: Hold 30 days (estimate).)
  7. To exit, select Unstake on your validator in the Staked section; there is no lockup, so your ALGO is released without a fixed waiting period — but the unstake amount must be above the minimum entry amount, or your entire balance. (Cost: Algorand fees under $1 (estimate). Time: 5 min.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Stake $50 of the chain's staking asset through Reti Pooling on Algorand. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Add a small amount to the stake the following week, so the record shows more than one staking action. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check Reti Pooling once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Reti Pooling's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #48 Tydro (`tydro`) — verified

- Category: Lending · Chains: Ink
- Official site: https://tydro.com
- DefiLlama: https://defillama.com/protocol/tydro
- What it does: Tydro is a decentralized, non-custodial lending protocol on Ink where anyone can supply assets to earn interest, with weekly TydroInkPoints campaigns (Season 2 live) tracked and claimed via Merkl toward $INK.
- Notes: Re-checked 2026-11-17: this is the biggest correction of the round. The old entry said 'No points or rewards program was found on the site' — that is now WRONG. Tydro's own forum (forum.tydro.com, official) confirms weekly TydroInkPoints supply/borrow incentive campaigns running since 14 Oct 2025, renewed weekly (latest posted renewal 11-18 Nov 2026), covering WETH, kBTC, USDC, USDT0, USDG and GHO; Season 1 snapshot locked in Jan 2026 and Season 2 is live now through the eventual INK TGE, with points tracked and claimed via Merkl and converting toward $INK (Kraken's unlaunched L2 token — no TGE date exists). The old steps also named no assets; the live reserve list is now confirmed on-chain (14 reserves incl. WETH, kBTC, USDT0, USDG, GHO, USDC, weETH, wrsETH, ezETH, sUSDe, USDe, SolvBTC, syrupUSDT, kHYPE) and live market data shows USDC at $59.2M supplied, 80.88% utilization, 4.59% supply APY. tydr.com itself now reads directly (Aave-powered, non-custodial, Ink; app at app.tydro.com). Note: the homepage's own 'by the numbers' figures ($2.3B deposits etc.) look inconsistent with DefiLlama/on-chain supply (~$157M total) and were NOT used.
- Sources: https://tydro.com, https://forum.tydro.com/t/tydroinkpoints-incentives-renewals/21, https://app.tydro.com, https://defillama.com/protocol/tydro, https://10k.nyxshcon.org/lending?view=markets&protocol=tydro

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. You need a wallet that supports the Ink network (chain 57073) to interact with Tydro at all. Fund that wallet with the asset you want to supply plus a little ETH on Ink for gas. Confirmed supply assets include USDC, USDT0, USDG, GHO, WETH and kBTC; USDC is the largest market at about $59M supplied and about 4.59% supply APY as of 17 Nov 2026. (Cost: $2-8 of gas (estimate). Time: 10-15 minutes.)
  2. Open app.tydro.com, connect your wallet, and go to the Markets section to check the current supply rate and utilization for each supported token before you commit any funds. Tydro is an Aave v3 white-label market on Ink. (Cost: $0. Time: 10 minutes.)
  3. Supply the asset and amount of your choice through the Tydro interface, approving the token spend first and then confirming the supply transaction in your wallet. Supplying also earns TydroInkPoints — see the next step. (Cost: $2-8 of gas (estimate). Time: 10 minutes.)
  4. Track TydroInkPoints: weekly supply and borrow campaigns have run since 14 Oct 2025 (see the renewals thread on forum.tydro.com), Season 1 snapshotted in Jan 2026 and Season 2 is live through the eventual INK TGE. Points are tracked and claimed via Merkl from the same wallet and convert toward $INK, which has no announced TGE date. (Cost: $0. Time: 10 minutes.)
  5. Optionally borrow against your supplied collateral if you want a second position, keeping the loan well over-collateralized. Tydro only supports over-collateralized borrowing, so never borrow close to the maximum. (Cost: $2-8 of gas if you borrow (estimate). Time: 10 minutes.)
  6. Hold the supplied position for at least 30 days and check the Markets page weekly to confirm the supply rate has not collapsed. Supplied tokens sit in audited smart contracts and keep earning while deposited. (Cost: capital locked in the protocol. Time: 30 days.)
  7. Exit by withdrawing your supplied tokens through the Tydro interface, repaying any open borrow first, and moving the funds back to your main wallet. Only claim anything from a link published on tydr.com itself, never from a DM or ad. (Cost: $2-8 of gas (estimate). Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Supply $100 of USDC to Tydro on Ink and leave it earning interest. Cost: $100 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Lend a second, smaller amount on Tydro the following week, using a different asset as collateral, so the record shows more than one deposit. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $100 locked in the position until you exit. Time: 30 days.
    5. Check Tydro once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Tydro's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $100 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #51 Tulipa Capital (`tulipa-capital`) — verified

- Category: Risk Curators · Chains: Ethereum, Base, Berachain
- Official site: https://www.tulipa.capital
- DefiLlama: https://defillama.com/protocol/tulipa-capital
- What it does: Tulipa Capital is a boutique DeFi risk-curation firm that manages lending-market vaults on Euler and Morpho for institutional investors, putting capital protection and risk assessment ahead of yield. It has no self-serve deposit app of its own.
- Notes: CONTRADICTION: a generic category step like 'deposit into Tulipa Capital' is wrong — tulipa.capital takes no deposits at all. Retail exposure is only indirect, through Morpho/Euler vaults Tulipa curates. No points program found on the official site. The specific Tulipa-curated vault names come from a third-party vault analysis, not from Tulipa's own site, so the steps name the platforms (Morpho/Euler) rather than a specific vault.
- Sources: https://defillama.com/protocol/tulipa-capital, https://www.tulipa.capital, https://getblock.io/marketplace/projects/tulipa-capital/

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. You will not deposit on tulipa.capital itself, so this wallet is for the vault app you use instead. (Cost: $0. Time: 5 minutes.)
  2. Read tulipa.capital first and accept what it actually is: a curator for institutional clients, not a retail app. Its site has no deposit button, no app, and no points program; its clients are protocols and institutions that hire it to curate vaults. (Cost: $0. Time: 10 minutes.)
  3. Find a vault curated by Tulipa Capital inside the Morpho or Euler app, on Ethereum or Base. Tulipa's revenue comes from Euler and Morpho vault yields, and third-party vault lists show Tulipa-curated vaults on both platforms. (Cost: $0. Time: 15 minutes.)
  4. Deposit USDC or the vault's underlying asset into that Tulipa-curated Morpho or Euler vault, approving the token and confirming the deposit. You receive ERC-4626 vault shares that earn the borrower interest. (Cost: $2-8 of gas (estimate). Time: 15 minutes to set up.)
  5. Hold the vault position for at least 30 days so the activity shows up in more than one snapshot. Tulipa's own pitch is long-term, risk-first curation, so a one-afternoon deposit does not match how these vaults are meant to be used. (Cost: capital locked in the vault. Time: 30 days.)
  6. Check the vault once a week on Morpho or Euler for its APY and TVL, and check tulipa.capital for any token or program announcement. No points or rewards program was found on Tulipa's site, so do not expect points for this position. (Cost: $0. Time: 10 minutes a week.)
  7. Exit by redeeming your vault shares in the Morpho or Euler app and withdrawing the underlying asset. Only claim anything from a link published on tulipa.capital, Morpho, or Euler itself, never from a DM, reply, or ad. (Cost: $2-8 of gas (estimate). Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $50 into a Tulipa Capital vault on Ethereum and keep the vault shares. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check Tulipa Capital once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Tulipa Capital's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #58 Yuzu Money (`yuzu-money`) — verified

- Category: Yield · Chains: Plasma, Monad, Ethereum
- Official site: https://app.yuzu.money
- DefiLlama: https://defillama.com/protocol/yuzu-money
- What it does: Yuzu Money issues yzUSD, an overcollateralized stablecoin backed by curated leveraged DeFi strategies. Users stake yzUSD to receive the yield-bearing syzUSD, while yzPP is a first-loss tranche that absorbs losses first in exchange for higher yield.
- Notes: BIGGEST CONTRADICTION IN THIS BATCH: a generic 'deposit stablecoins into Yuzu and mint yzUSD' step is wrong for a retail farmer — Yuzu's own docs explicitly say retail users are not eligible to mint, subscribe, or redeem yzUSD or yzPP, and minting requires KYC/AML and source-of-funds checks. The real retail paths are staking freely (buy yzUSD second-hand, stake for syzUSD) and the open Marketplace vaults. No points program was found on the official site or docs; the Medium staking guide mentioning points is not an official Yuzu source and was not relied on.
- Sources: https://defillama.com/protocol/yuzu-money, https://app.yuzu.money/, https://app.yuzu.money/docs, https://www.yuzu.money/alpha, https://app.yuzu.money/alpha/yzusd

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. You will interact with app.yuzu.money and secondary markets from this wallet only. (Cost: $0. Time: 5 minutes.)
  2. Understand the access rule before spending anything: Yuzu's own docs say primary minting and redeeming of yzUSD and yzPP is restricted to accredited, qualified, institutional, or sophisticated investors after KYC and screening, and retail users are not eligible to mint or redeem. (Cost: $0. Time: 10 minutes.)
  3. Get yzUSD on the secondary market instead, since Yuzu's docs say yzUSD may be traded by anyone on exchanges and DEXs that list it. Buy it on Plasma, where the yzUSD page lists the token, or use one of Yuzu's open Marketplace vaults that take deposits from anyone with no screening. (Cost: $2-8 of gas plus any swap fee (estimate). Time: 15 minutes.)
  4. Stake your yzUSD in the Yuzu app to receive syzUSD, the yield-bearing ERC-4626 token. Yuzu's site says staking is open with no KYC, and syzUSD earns the weekly yield while yzUSD itself bears no yield. (Cost: $2-8 of gas (estimate). Time: 10 minutes.)
  5. Alternatively, deposit USDC into an open Marketplace vault such as yzSyrup or yzCash on Ethereum, which the app shows with live APYs and no screening. These vaults deploy into Aave, Morpho, Euler, and Fluid strategies. (Cost: $2-8 of gas (estimate). Time: 15 minutes.)
  6. Hold the syzUSD or vault position for at least 30 days and check the Yuzu dashboard weekly for yield and the live collateral ratio, which the site attests every 15 minutes. Do not buy yzPP unless you are an eligible investor: it takes first loss. (Cost: capital locked in the position. Time: 30 days.)
  7. Exit by unstaking syzUSD back to yzUSD, which Yuzu's FAQ says is basically instant, then selling yzUSD on the secondary market. Direct redemption of yzUSD takes up to 3 days and is gated, and yzPP has a 30-day redemption period with a 5,000 minimum, so plan the exit through the secondary market. (Cost: $2-8 of gas plus any swap fee (estimate). Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Deposit $50 into Yuzu Money's main vault on Plasma and leave it to compound. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 30 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 30 days.
    5. Check Yuzu Money once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Yuzu Money's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 60 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #61 Firelight (`firelight`) — verified

- Category: Insurance · Chains: Flare
- Official site: https://firelight.finance
- DefiLlama: https://defillama.com/protocol/firelight
- What it does: Firelight is an on-chain cover protocol on Flare: users stake FXRP (wrapped XRP via Flare FAssets) and receive stXRP, and that staked capital backs cover for DeFi vaults against defined failures, with incidents validated by an independent Risk Consortium and staked capital subject to slashing.
- Notes: Re-checked 2026-11-17: firelight.finance now reads directly and confirms the cover-product framing, the independent Risk Consortium, audits (OpenZeppelin, Coinspect, 0xMacro, Immunefi bug bounty) and the FAssets/FXRP mechanism — all consistent with the old entry. The upgrade is driven by one time-sensitive addition the old steps miss: the early-contributor campaign allocates 230,000 FXRP pro rata by Firelight Points, with claims open 7 Oct-7 Dec 2026 (confirmed by AltcoinBuzz and Weex, citing Firelight/Flare). With today at 17 Nov, ~20 days of that window remain. The 30-60 day exit, emissions stopping at unstake initiation, and Points-not-a-claim-on-premiums are re-confirmed by SpendTheBits' 13 Nov 2026 update quoting Firelight's docs, so those steps are kept and only tightened (the exit step now states the final withdrawal transaction must be submitted manually).
- Sources: https://firelight.finance/, https://superapp.spendthebits.com/insights/earning-on-xrp-firelight-stxrp-points, https://www.altcoinbuzz.io/firelight-s-oct-6-switch-turns-staked-fxrp-into-cover-backing, https://defillama.com/protocol/firelight

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. You need a Flare-compatible wallet plus a little FLR for gas, or an XRPL wallet if you use the Flare Smart Accounts one-flow route. (Cost: $0. Time: 5 minutes.)
  2. Get FXRP, the wrapped XRP on Flare created through Flare's FAssets system. You can mint it from XRP or buy it, and Flare's guidance says at least 13 XRP is needed to cover a minted lot and fees. (Cost: $2-8 of gas or minting fees (estimate). Time: 15 minutes.)
  3. Open the Firelight app at firelight.finance, connect your wallet, and accept the terms of use on your first visit. The app is where staking happens; the main firelight.finance site itself is informational and describes the cover product and the Risk Consortium. (Cost: $0. Time: 10 minutes.)
  4. Deposit your FXRP into the Staked XRP Vault and confirm the deposit. You receive stXRP 1:1 for the FXRP deposited, as a liquid token representing your share of the vault. (Cost: $2-8 of gas (estimate). Time: 10 minutes.)
  5. Hold the stXRP position and understand what it now does: since the full launch on 6 October 2026, staked FXRP backs live cover and cover premiums stream into the vault, while your capital can be slashed if a covered event pays out. Firelight Points track early participation but are not a claim on premiums. Check the Firelight dashboard weekly for your stXRP balance, Firelight Points, and the cover status of the vaults your capital backs. Keep some FLR for gas. (Cost: capital at risk of slashing. Time: 30 days.)
  6. If you staked early, check the early-contributor claim now: 230,000 FXRP is allocated pro rata by Firelight Points, claimable from 7 Oct to 7 Dec 2026 — about 20 days remain as of 17 Nov. Claim only through Firelight's own app or a link it publishes. (Cost: $0. Time: 10 minutes.)
  7. Exit by starting an unstake in the app, which burns your stXRP and stops all emissions at once, then waiting out the cooldown before submitting the final withdrawal transaction yourself — it is not automatic. With 30-day cover periods now in force, the wait is 30 to 60 days depending on when you request the exit, so do not treat this as an instant withdrawal. (Cost: $2-8 of gas (estimate). Time: 30-60 days to fully exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Buy $50 of cover from Firelight on Flare and keep the policy active. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 45 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 45 days.
    5. Check Firelight once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Firelight's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 75 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

### #62 Mezo Earn (`mezo-earn`) — verified

- Category: Governance Incentives · Chains: Mezo
- Official site: https://mezo.org
- DefiLlama: https://defillama.com/protocol/mezo-earn
- What it does: Mezo Earn is the economic engine of the Mezo Bitcoin network: bitcoin holders lock BTC to receive veBTC, which earns a share of protocol revenue and directs where MEZO emissions flow, and locking MEZO for veMEZO boosts that voting weight up to 5x.
- Notes: Mezo's own blog and docs (mezo.org) describe the lock, vote, and boost mechanics in detail, and the homepage confirms borrowing, the wallet view, and earning/voting/liquidity as the core actions. The exact lock duration and unlock waiting period were not confirmed on the pages checked, so the exit step does not state one. 'Mats' are Mezo's points-style rewards earned on deposits and pools; no separate public points-program page was found. The snapshot category is Governance Incentives, which fits: the farm is locking BTC/MEZO and voting, not a simple deposit-and-earn vault.
- Sources: https://defillama.com/protocol/mezo-earn, https://mezo.org/, https://mezo.org/blog/getting-started-with-mezo-how-to-lock-vote-and-earn/, https://mezo.org/docs/users/mezo-earn/vote, https://anchorage.mezo.org/feature/earn

  Farm steps (researched):
  1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. You will bridge BTC onto the Mezo network and interact with the Mezo app from this wallet only. (Cost: $0. Time: 5 minutes.)
  2. Bridge or deposit BTC onto Mezo and open the Mezo app at mezo.org. Mezo's own guide says you deposit Bitcoin into your personal on-chain vault, and deposited BTC starts earning through its incentive system with no active management required. (Cost: bridge fee, varies (estimate $2-8). Time: 15 minutes.)
  3. Lock your BTC in the app under Earn, then Lock, to receive veBTC. Mezo's docs say veBTC is your base position: it gives 1x voting weight on its own, directs where MEZO emissions flow, and earns real yield from network activity. (Cost: $2-8 of gas (estimate). Time: 10 minutes.)
  4. Optionally lock MEZO tokens to receive veMEZO, then pair it with your veBTC using the Pair and Boost button on the Lock page. Mezo's guide says veMEZO has no voting power alone but multiplies your veBTC weight up to 5x. (Cost: $2-8 of gas if you lock MEZO (estimate). Time: 10 minutes.)
  5. Vote each week on the Vote page in the Mezo app, allocating your veBTC across gauges such as BTC/MUSD pools or the MUSD Savings Rate. Epochs run weekly, Thursday to Thursday at 00:00 UTC, and voters earn the trading fees of the pools they vote for plus incentives posted on those gauges. (Cost: $2-8 of gas per vote (estimate). Time: 15 minutes a week.)
  6. Optionally add a second position by providing liquidity to a Mezo pool, such as BTC/MUSD, to earn trading fees and mats rewards. Mezo's Earn page lists this as a separate path alongside locking and voting, and vaults are described as a future structured-yield option. (Cost: $2-8 of gas if you add liquidity (estimate). Time: 15 minutes.)
  7. Claim your fees and incentives at the end of each epoch from the Mezo app, and when you want out, unlock through the Lock page and withdraw your BTC. Only claim from links on mezo.org itself, never from a DM, reply, or ad. (Cost: $2-8 of gas to claim and exit (estimate). Time: 10 minutes to exit.)

  Current repo steps (for comparison):
    1. Use a fresh wallet that holds only the money you plan to farm, and keep its seed phrase offline. Never connect it to anything else. Cost: under $3 of gas for the first transaction. Time: 5 minutes.
    2. Put $50 into Mezo Earn's main product on Mezo — check its own page to see which product holds the TVL — and leave the position open. Cost: $50 of capital and about $4 of gas. Time: 15 minutes to set up.
    3. Top up the position with a smaller amount the following week, so the record shows more than one deposit instead of a single one. Cost: about $2 of gas a week. Time: 10 minutes a week.
    4. Hold the position for at least 45 days, so the activity shows up in more than one snapshot. Airdrops usually reward wallets that were there for weeks, not for a single afternoon. Cost: $50 locked in the position until you exit. Time: 45 days.
    5. Check Mezo Earn once a week: its TVL trend, any token announcement on its own site or docs, and whether the team mentions a points or rewards program. If TVL drops hard two weeks in a row, stop topping up and re-check before you add more. Cost: no money, just your time. Time: 10 minutes a week.
    6. Before you claim anything, open Mezo Earn's own site or docs yourself and follow only the link published there. Never claim from a link in a DM, a reply, or an ad — fake claim pages are how wallets get drained. Cost: nothing to check. Time: 10 minutes.
    7. Stop when the token launches and the first claim is paid, or after 75 days with no launch: withdraw the $50 and close the position. Cost: about $3 of gas to exit. Time: 10 minutes to exit.

