# eth-btc-dominance-strategy

A backtested trading strategy that goes long on Ethereum when both ETH and BTC are in an uptrend, and Ethereum shows dominance over Bitcoin (ETH/BTC uptrend).

🧠 Strategy Overview — ETH/BTC Dominance

This strategy is a long-only momentum model focused on Ethereum (ETH), designed to ride strong trends while avoiding weak or manipulated market conditions. It uses Bitcoin (BTC) and ETH/BTC ratio as trend confirmation filters to increase edge and robustness.

⸻

✅ Entry Conditions — All Must Be True

We enter a long position on ETH only when all three of the following conditions are satisfied:
	1.	ETH is in an uptrend
→ ETH price is above its own moving average (e.g. 100-period MA)
	2.	BTC is in an uptrend
→ BTC price is above its own moving average (e.g. 60-period MA)
	3.	ETH is outperforming BTC (ETH is dominating)
→ The ETH/BTC ratio is rising
→ Specifically, a short-term moving average of ETH/BTC is above its long-term moving average
→ This shows ETH is gaining strength relative to BTC

⸻

❌ Exit Conditions — Any One Is Enough

We exit the position as soon as any of the following exit conditions are met:
	1.	Trend Reversal Detected
→ ETH price drops more than a threshold below its moving average
→ Suggests a weakening trend
	2.	Stop-Loss Triggered
→ Trade incurs a loss greater than -1.5%
→ Protects against large unexpected drawdowns
	3.	Take-Profit Triggered
→ Trade reaches +4% gain
→ Locks in profits on sharp moves
	4.	Volume Anomaly Detected
→ Unusually high volume (e.g. 6× average volume)
→ But with a very small candle body (low price movement)
→ Indicates potential hidden selling, exhaustion, or manipulation
→ We exit to avoid unfavorable conditions

⚠️ Disclaimer

Please note that maximum drawdown (MaxDD) may be underestimated in this strategy.
This is because the stop-loss logic is based on the close of each 5-minute candle, and not on intrabar (tick-by-tick or second-level) data.

Since second-level historical data is not available, it’s impossible to detect price spikes or wicks that could have triggered a stop-loss mid-candle.
Therefore, in real-world conditions, the drawdown could be slightly higher than shown in the backtest.
<img width="552" height="83" alt="Capture d’écran 2025-10-17 à 13 26 06" src="https://github.com/user-attachments/assets/edb26d06-cf34-4be5-98ed-f8bbcfe69cc1" />

<img width="1091" height="439" alt="Capture d’écran 2025-10-17 à 13 26 13" src="https://github.com/user-attachments/assets/d3c0577d-954a-4b92-9e25-8e77ee607aee" />
<img width="531" height="320" alt="Capture d’écran 2025-10-17 à 13 26 19" src="https://github.com/user-attachments/assets/435d930b-f843-46ff-8fb3-eff7b8f949d0" />
<img width="323" height="207" alt="Capture d’écran 2025-10-17 à 13 26 15" src="https://github.com/user-attachments/assets/13ddd8aa-89c2-4b68-92e2-2126540ff62f" />
