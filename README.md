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

We exit the ETH position if any of the following conditions occur:
	1.	ETH breaks below its moving average
➤ Indicates a possible trend reversal
	2.	Stop-loss is triggered at -3%
➤ Capital protection during unexpected drops
	3.	Volume anomaly without price movement
➤ ETH trading volume spikes significantly
➤ But the candle body is very small (suggesting weak price conviction)
➤ Possible sign of manipulation, exhaustion, or hidden selling pressure


<img width="524" height="88" alt="Capture d’écran 2025-10-16 à 18 27 53" src="https://github.com/user-attachments/assets/0983c393-160f-4d32-8d74-00d30d02b62e" />
<img width="348" height="175" alt="Capture d’écran 2025-10-16 à 18 27 48" src="https://github.com/user-attachments/assets/cb5cbf17-ebed-4cb5-abef-28d4e60d7363" />
<img width="1087" height="527" alt="Capture d’écran 2025-10-16 à 18 28 03" src="https://github.com/user-attachments/assets/e268ad14-1998-4273-8ba0-e410cd3893aa" />
