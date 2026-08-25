# Pattern Performance Audit — 2026-08-25

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1148. With forward data: 1134.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 626 | 42.0% | -1.75% | 36.4% | -2.31% | 32.4% | -4.32% |
| 🌀 Coil | 419 | 41.9% | -0.09% | 36.1% | -1.42% | 32.0% | -5.55% |
| 📍 Near | 89 | 28.7% | -4.18% | 39.1% | -4.72% | 35.6% | -6.35% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 569 | 42.5% | -1.72% | 35.7% | -2.61% | 31.1% | -6.32% |
| tier2 | 565 | 39.3% | -0.92% | 37.3% | -1.71% | 33.9% | -3.55% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 711 | 36.0% | -3.21% | 31.3% | -6.67% |
| 90-94 | 283 | 39.2% | 1.37% | 35.7% | 0.02% |
| 85-89 | 140 | 33.6% | -4.15% | 32.1% | -6.35% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 138.89 | +132.2% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 138.89 | +132.2% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 138.89 | +132.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 138.89 | +129.3% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 138.89 | +120.6% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 138.89 | +119.3% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 138.89 | +118.2% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 138.89 | +118.1% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 138.89 | +115.5% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| NVTS | 06-17 | 🌀 Coil | 97.5 | 22.34 | 11.46 | -48.7% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| AXTI | 06-03 | 📍 Near | 100.0 | 106.70 | 56.62 | -46.9% |
| NVTS | 06-16 | 🌀 Coil | 97.5 | 22.09 | 11.76 | -46.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
