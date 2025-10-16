# eth-btc-dominance-strategy

A backtested trading strategy that goes long on Ethereum when both ETH and BTC are in an uptrend, and Ethereum shows dominance over Bitcoin (ETH/BTC uptrend).

🧠 Strategy Overview — ETH/BTC Dominance

This strategy is a long-only model on Ethereum, designed to enter and exit positions based on trend strength and volume-price behavior.

⸻

✅ Entry Conditions (all must be true)

We enter a long position on ETH only when the following three conditions are met:
	1.	Ethereum is in an uptrend
➤ ETH price is above its moving average
	2.	Bitcoin is in an uptrend
➤ BTC price is above its moving average
	3.	Ethereum is dominating Bitcoin
➤ The ETH/BTC ratio is in an uptrend
➤ Defined as a short-term moving average of ETH/BTC being above the long-term moving average

⸻

❌ Exit Conditions (any one is enough)
<img width="1087" height="527" alt="Capture d’écran 2025-10-16 à 18 28 03" src="https://github.com/user-attachments/assets/197d7a34-dfbf-4894-82b2-3f48145ef866" />

We exit the ETH position if any of the following conditions occur:
	1.	ETH breaks below its moving average
➤ Indicates a possible trend reversal
	2.	Stop-loss is triggered at -3%
➤ Capital protection during unexpected drops
	3.	Volume anomaly without price movement
➤ ETH trading volume spikes significantly
➤ But the candle body is very small (suggesting weak price conviction)
➤ Possible sign of manipulation, exhaustion, or hidden selling pressure
