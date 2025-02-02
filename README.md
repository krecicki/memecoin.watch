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
