# Pattern Performance Audit — 2026-09-10

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1185. With forward data: 1166.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 632 | 40.9% | -1.98% | 39.0% | -2.48% | 38.0% | -3.1% |
| 🌀 Coil | 433 | 42.3% | -0.29% | 36.6% | -1.73% | 40.2% | -3.86% |
| 📍 Near | 101 | 33.0% | -3.7% | 43.3% | -4.84% | 46.4% | -3.26% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 595 | 43.2% | -1.66% | 38.1% | -2.99% | 38.1% | -4.82% |
| tier2 | 571 | 38.1% | -1.34% | 38.9% | -1.79% | 41.0% | -1.91% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 728 | 38.7% | -3.39% | 40.6% | -4.62% |
| 90-94 | 281 | 40.1% | 1.03% | 39.8% | 0.65% |
| 85-89 | 157 | 34.2% | -4.07% | 34.2% | -5.04% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 135.61 | +123.9% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 135.61 | +115.4% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 135.61 | +114.2% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 135.61 | +113.1% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 135.61 | +113.0% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 135.61 | +110.4% |

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
| BTDR | 06-30 | 🌀 Coil | 87.8 | 15.87 | 8.90 | -43.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
