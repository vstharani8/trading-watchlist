# Pattern Performance Audit — 2026-09-02

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1198. With forward data: 1181.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 643 | 42.0% | -1.6% | 34.4% | -2.69% | 28.6% | -5.04% |
| 🌀 Coil | 441 | 41.0% | -0.0% | 34.3% | -1.7% | 29.5% | -5.52% |
| 📍 Near | 97 | 33.3% | -3.17% | 41.7% | -4.43% | 39.6% | -5.2% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 603 | 42.2% | -1.6% | 34.2% | -2.89% | 28.0% | -6.49% |
| tier2 | 578 | 39.6% | -0.65% | 35.8% | -2.02% | 31.8% | -3.93% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 746 | 34.2% | -3.59% | 28.3% | -7.18% |
| 90-94 | 288 | 38.2% | 1.35% | 33.7% | 0.38% |
| 85-89 | 147 | 32.4% | -4.21% | 30.3% | -6.35% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 154.27 | +157.9% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 154.27 | +157.9% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 154.27 | +157.9% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 154.27 | +154.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 154.27 | +145.0% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 154.27 | +143.6% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 154.27 | +142.4% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 154.27 | +142.3% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 154.27 | +139.3% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 154.27 | +139.3% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| NVTS | 06-17 | 🌀 Coil | 97.5 | 22.34 | 11.46 | -48.7% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| NVTS | 06-16 | 🌀 Coil | 97.5 | 22.09 | 11.76 | -46.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |
| NVTS | 06-12 | 📐 Tight | 96.8 | 23.39 | 13.09 | -44.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
