# memecoin.watch
The official repository for memecoin.watch on the Solana network

# memecoin.watch User Guide
<img width="700" alt="memecoin scanner" src="https://github.com/user-attachments/assets/b3a83299-736f-4ff4-8ba6-02cf8206ae2c" />
<img width="700" alt="trade meme coins" src="https://github.com/user-attachments/assets/a5dd1501-dd8d-42de-8ffd-65cc4035667f" />


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

## Scanner Overview <a name="scanner-overview"></a>

| Scanner | Purpose | Key Metric | Ideal For |
|---------|---------|------------|-----------|
| **Early Warning** | Pattern detection | 0-10 score | Early entries |
| **Pump Detector** | Volume heat | Heat % | Momentum |
| **Big Swap** | Whale tracking | Buy clusters | Accumulation |

---

## Early Warning Scanner <a name="early-warning-scanner"></a>
### Pattern Detection Engine  
```python
if consecutive_buys >=5 and volume_spike:
    increase_score()
```

**Key Features**:
- Score calculation (0-10)
- New wallet detection (<24h old)
- Rug-check automation
- Buy sequence analysis

---

## Pump Detector <a name="pump-detector"></a>
### Heat Formula  
`HEAT = (1m Volume / 5m Volume) * 100`

**Threshold Guide**:
| Heat | Status | Action |
|------|--------|--------|
| <33% | Cold | Watch |
| 33-49% | Warming | Prepare |
| 50-99% | Hot | Trade |
| 100%+ | Overheated | Caution |

---

## Big Swap Detector <a name="big-swap-detector"></a>
### Whale Activity Types  
1. **Single Whale**  
   `120 SOL (1 buy)`  
2. **Buy Cluster**  
   `80 SOL (20 buys @ 4 SOL avg)`

---

## Signal Strategies <a name="signal-strategies"></a>
**Best Combination**:  
1. Early Warning ≥7/10  
2. Heat ≥40%  
3. Cluster ≥10 buys  

**Red Flags**:
- Score <5 + new wallets
- Heat >100% + no swaps

---

## Safety Systems <a name="safety-systems"></a>
**Auto-Protections**:
- ✅ Freeze authority check
- 🕵️ Wallet age analysis
- 🤖 Bot pattern detection
- 📦 Bundle transaction flagging

---

## Trading Tools <a name="trading-tools"></a>
**Jupiter Swap Flow**:  
1. Click token's **Trade** button  
2. Check price impact  
3. Set slippage (1-5%)  
4. Confirm swap  

---

## Examples <a name="examples"></a>
**Successful Trade Setup**:  
```yaml
Early Warning: 8/10 (5 buys, 3 price steps)
Pump Detector: Heat 58% (Buy/Sell 110x)
Big Swap: 15 buys @ 6.2 SOL avg
```

**Result**: 215% gain in 28 minutes

---

[⬆ Back to Top](#memecoinwatch-user-guide)
