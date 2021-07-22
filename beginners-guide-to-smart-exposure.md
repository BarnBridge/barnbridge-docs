# Beginner's Guide to SMART Exposure

## What Is SMART Exposure?

SMART Exposure allows users to passively maintain a specific ratio within an underlying ERC-20 token pair. For example, if you want to track ETH relative to Bitcoin, you might want to hold a target allocation of 50% ETH and 50% wBTC. Similarly, if you want to track DeFi’s relative performance against Ether, you could enter a 50% DPI \(Index Coop’s DeFi Index token\) and 50% ETH SMART Exposure position. SMART Exposure offers these types of risk-adjusted retargeting strategies in a convenient and non-custodial way, potentially outperforming buy-and-hold strategies under certain market conditions.

This functionality is possible because SMART Exposure maintains its own asset pools. Users are able to deposit the ERC-20 assets they want to balance, select from popular ratios to maintain, and then have them be recalibrated automatically.

![](.gitbook/assets/image%20%2811%29.png)

SMART Exposure positions are rebalanced after either a time-based or ratio deviation threshold is met. Once the position ratio deviates from its target more than that defined threshold, or the time since the last rebalance exceeds the defined rebalancing frequency, a rebalance is triggered by keeper bots. Rebalancing gas costs are covered from the underlying pooled collateral which makes it much cheaper compared to individual rebalance transactions. Thresholds can be set for every SMART Exposure pool through DAO vote. In our internal back testing, values between 5–10% deviation performed best.

The default rebalance method currently is flash swapping via Sushiswap.

## Secondary Liquidity with Exposure Tokens \(eTokens\) <a id="c504"></a>

SMART Exposure can support up to 5 different ratios \(i.e., “tranches”\) for any token pair. Each exposure ratio is represented by a fungible ERC-20 token — making it easy to switch between strategies, buy or sell it on secondary markets, and potentially use it as collateral in other protocols.

Exposure tokens have their own tickers. For example, the exposure token for the wBTC 50%, ETH 50% is called bb\_ET\_ETH50/WBTC50, where:

* `bb` — BarnBridge
* `ET` — exposure token
* `ETH50/WBTC50` — ETH 50%, wBTC 50%

Users receive eTokens marking their positions upon depositing the underlying tokens to the pool. The amount deposited can be provided in one or both of the underlying assets. Exposure tokens can then be traded on secondary markets or redeemed for the underlying assets in the SMART Exposure pools. Users may also swap their eTokens for different exposure ratios between the same pools.

## Why Use SMART Exposure?



SMART Exposure tokens provide multi-asset HODLers with an opportunity to passively diversify their portfolios and navigate volatile crypto markets.

Other protocols also use rebalancing token pairs but are optimized for other use cases and have chosen different trade-offs. Our lightweight approach provides the following advantages to other protocols:

**a\) AMM Pools**

* **Higher alpha**: SMART exposure’s rebalancing strategy provides higher excess returns relative to AMMs. For volatility harvesting, the continuous rebalancing of AMMs underperforms especially when fee income isn’t taken into account.
* **Better rates:** Rebalancing amounts are swapped at the external market price \(provided by Chainlink\).

**b\) Open Market Operation-Based Portfolio Managers**

* **Automated**: Our keeper network takes care of the rebalancing without the need for additional coordination \(phases\), market makers, dutch auctions, etc.
* **More lightweight**: We have stripped SMART Exposure tokens to a bare minimum — thus, they are a more efficient and scalable approach to portfolio building.
* **Higher liquidity for different exposures ratios** of the same token pair as they tap into the same liquidity pool.

SMART Exposure is best suited for fixed allocation strategies and for efficient treasury management because it is:

* **Passive Management:** Fully automated rebalancing removes the need for manual monitoring and adjusting of position risk.
* **Convenient:** Adjusting risk exposure for any asset pair is as straightforward as just buying/selling your ERC-20 exposure token.
* **Efficient:** Rebalancing strategies are executed predictably and with minimal slippage.
* **Potentially Tax Optimized**: In jurisdictions that tax in kind crypto transactions, SMART Exposure may remove the tax implications associated with rebalancing on your own. Each jurisdiction is different, however, and you should always seek professional advice to assess your particular situation.
* **Composable**: As eTokens are fungible ERC-20 tokens they can be easily integrated into other protocols and services, or even be used as collateral.

## Rebalancing versus Buy-and-Hold

The probability to outperform buy and hold strategies are the highest with:

* **Sideways Markets**: Constant oscillations in a given ratio increase the opportunity for volatility harvesting through rebalancing.
* **Volatile Assets**: More fluctuations in asset price present more opportunities for rebalancing.
* **Non-Correlated Assets**: Non-correlation results in greater ratio volatility.
* **Mid- to Long-Term Time Horizon**: Volatility harvesting is most likely to outperform buy and hold strategies over longer timeframes.

You can refer to our backtesting [here](https://drive.google.com/file/d/1fro709VIAkD_ad9gkgyVR27BO7K_Jmy0/view) to see how daily rebalances for popular 50:50 pairs outperformed AMM strategies over time. Namely:

### **For ETH/USD:**

![](.gitbook/assets/image%20%2814%29.png)

### **For BTC/USD:**

![](.gitbook/assets/image%20%2812%29.png)

### **For BTC/ETH**

![](.gitbook/assets/image%20%2817%29.png)

## Security & Audits

We successfully passed through an audit by Haechi on May 5th. It’s available here: [Haechi audit](https://github.com/BarnBridge/BarnBridge-PM/blob/master/audits/BarnBridge%20SMART%20Exposure%20audit%20by%20Hacken.pdf).

