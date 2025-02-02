# memecoin.watch
The official repository for memecoin.watch on the Solana network

"Why use bull-x if those scanners are free on ape.pro? Why is memecoin.watch different or worth my money?"

At memecoin.watch we built three AI scanners: the yellow one watches every large Raydium trade (back run trades, since you cannot front run on Solana, there is no meme pool), the red one analyzes buying volume patterns (based on people building positions high on the buy side), and the green one catches early moves before they pump (this is possible by using GenAI to train models to identify imminent pumps). Other services bet on new coins, recently migrated coins, and about-to-migrate coins. We trained AI on millions of transaction logs to spot real pumps before they're obvious - not just scanner filters. You saw what bull-x and ape.pro both missed. Ready to see the next ones before they do?

You can trade directly from alerts on our website (powered by Jupiter)

# memecoin.watch User Guide
![memecoin scanner](https://github.com/user-attachments/assets/b3a83299-736f-4ff4-8ba6-02cf8206ae2c)

---
## Table of Contents  
1. [Scanner Overview](#scanner-overview)  
2. [Early Warning Scanner](#early-warning-scanner)  
3. [Pump Detector](#pump-detector)  
4. [Big Swap Detector](#big-swap-detector)  
5. [Signal Strategies](#signal-strategies)  
6. [Safety Systems](#safety-systems)  
7. [Trading Tools](#trading-tools)  
8. [Examples](#examples)  

---
## Scanner Overview 
| Scanner | Purpose | Key Metric | Ideal For |
|---------|---------|------------|-----------|
| **Early Warning** | Independent pattern detection | 0-10 score | Early entries |
| **Pump Detector** | Independent volume heat | Heat % | Momentum |
| **Big Swap** | Independent whale tracking | Buy clusters | Accumulation |

**Important Note:** Each scanner operates completely independently. There is no way to correlate alerts between scanners. They are three separate tools monitoring the same network in different ways.

---
## Early Warning Scanner
This scanner independently looks for specific patterns before major moves.

The Raydium Early Scanner is a specialized monitoring system designed to catch emerging memecoin momentum on Solana before major price movements occur. By analyzing trading patterns across Raydium's pools, the scanner identifies legitimate buying pressure through a sophisticated scoring system that evaluates consecutive buys, volume ratios, and price step patterns. The system filters out common manipulation attempts by checking wallet age, bundle patterns, and token properties.

What sets this scanner apart is its focus on frozen tokens and legitimate wallet activity, helping separate real retail buying momentum from typical bot manipulation. Using expensive highspeed RPC endpoints & WSS, the system processes recent transactions in real-time while maintaining careful rate limiting to ensure consistent monitoring. Key metrics like buy ratios, consecutive order patterns, and price step analysis are combined into a weighted scoring system that has been trained on millions of historical memecoin trades to identify genuine pump setups before they become obvious to the broader market.

**Key Features:**
- Score calculation (0-10) based on multiple indicators
- Buy sequence analysis
- Price step detection (0.2% minimum increases)
- Automatic wallet age verification (<24h flagged)
- Token freeze checks (mint & freeze authority)
- Bundle transaction detection

**Example Output:**
```yaml
Score: 7/10
Buy Volume: 22.21 SOL
Buy/Sell Ratio: 93.74%
Price Change: 159.92%
Patterns: Consecutive buys, 2 price steps
```

---
## Pump Detector
Independent monitor for volume acceleration and buying pressure.

The Raydium Pump Scanner is designed to catch real memecoin momentum before the major moves happen. Unlike basic volume scanners, this system tracks sophisticated buying patterns across multiple time frames, specifically looking for accelerating buy pressure and sustained momentum. The scanner monitors both 5-minute and 1-minute windows to identify genuine retail buying waves, requiring consistent volume above 0.5 SOL in recent trades and a strong buy-to-sell ratio to filter out fake pumps and bot activity.

What sets this scanner apart is its focus on safety and momentum confirmation. Every detected token is automatically verified to have disabled mint and freeze authorities, protecting you from common rug pulls. The system's "heat" metric helps identify true momentum by measuring buy acceleration, requiring recent minute volume to exceed 20% of 5-minute volume while maintaining a healthy 1.2x buy/sell ratio. This multi-factor approach helps you spot legitimate retail buying waves before they become obvious to the broader market, while filtering out the usual manipulation that plagues memecoin trading.

### Heat Formula  
`Heat = (1min_volume / 5min_volume) * 100`

**Threshold Guide:**
| Heat | Status | Action |
|------|---------|---------|
| <33% | Cold | Monitor |
| 33-48% | Building | Alert |
| 48-99% | Hot | Active |
| 100% | Peak | Caution |

**Real Numbers:**
```yaml
Heat: 48.16%
Buy/Sell: 83.93x
5m Volume: 0.84 SOL
1m Volume: 0.40 SOL
```

---
## Big Swap Detector
Independently tracks significant Raydium transactions.

You can back run big players using the Raydium Big Swap Scanner is your early warning system for significant Solana memecoin moves, focusing on big swap activity through Raydium. The scanner tracks real-time trading and alerts you when meaningful volume starts flowing into a token - it monitors 5-minute windows for sustained buying pressure and requires multiple buys totaling over 3 SOL to trigger alerts, helping you spot real momentum while filtering out the noise of small trades under 0.1 SOL.
Before any alert hits your screen, the scanner verifies that the token's mint and freeze authorities are disabled (a critical safety check), and provides you with essential trade data including the 5-minute volume, number of buys, average buy size, and latest trade amount. By focusing purely on big swap detection and key safety verifications, you get clean, actionable alerts right when serious buying starts - giving you the early edge in catching legitimate momentum before the crowd.

**What You See:**
```yaml
Volume: 88.30 SOL
Buys: 21
Avg Size: 4.20 SOL
Last: 22.27 SOL
```

**Activity Types:**
1. **Buy Clusters**
   - Multiple related purchases
   - Growing average size
   - Increasing frequency

2. **Whale Entries**
   - Large individual trades
   - Sequential large buys
   - Volume spikes

---

## Signal Strategies
Each scanner provides different types of signals. These scanners operate independently and cannot be correlated.

**Early Warning Signals to Watch:**
```yaml
Score: ≥7/10
Patterns: Multiple indicators
Wallet: Clean history
```

**Pump Detector Signals to Watch:**
```yaml
Heat: 33-48%
Buy/Sell: >80x
Volume: Rising 1m/5m ratio
```

**Big Swap Signals to Watch:**
```yaml
Pattern: Multiple clusters
Size: Increasing averages
Frequency: Regular buys
```

**Red Flags (Per Scanner):**
- Early Warning:
  - New wallets (<24h) buying
  - Bundle transactions detected
  - Erratic patterns

- Pump Detector:
  - Heat 100% with tiny volume
  - Inconsistent volume spikes

- Big Swap:
  - Single massive buys without followup
  - Random size distribution

---
## Safety Systems Built in to Filter Out Tokens Automatically
**Auto-Protection:**
- ✅ Token freeze & mint verification
- 🕵️ Wallet age analysis (<24h)
- 📦 Bundle transaction flagging

---
![trade meme coins](https://github.com/user-attachments/assets/a5dd1501-dd8d-42de-8ffd-65cc4035667f)

## Trading Tools
**Jupiter Integration:**
1. One-click trading from alerts
2. Real-time price impact calculation
3. Slippage protection
4. Minimum received verification

**UI Features:**
- Show/Hide Pump.Fun filters per scanner
- Independent live status for each scanner
- Direct transaction links
- Token verification display

---
## Examples
**Note:** These are independent examples from each scanner. You cannot correlate alerts between scanners.

**Early Warning Activity:**
```yaml
Score: 8/10
Buy Volume: 22.21 SOL
Patterns: Consecutive buys, 2 price steps
```

**Separate Pump Detection:**
```yaml
Heat: 48.16%
Buy/Sell: 83.93x
5m Volume: Growing
```

**Independent Big Swap:**
```yaml
Buys: 21
Avg: 4.20 SOL
Pattern: Increasing sizes
```

---
[⬆ Back to Top](#memecoinwatch-user-guide)
