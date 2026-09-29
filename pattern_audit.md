# Pattern Performance Audit — 2026-09-29

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1179. With forward data: 1162.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 616 | 44.5% | -0.85% | 47.1% | 0.06% | 46.4% | 1.5% |
| 🌀 Coil | 440 | 45.7% | 0.61% | 44.1% | 0.3% | 46.4% | 0.09% |
| 📍 Near | 106 | 37.1% | -2.83% | 39.0% | -4.0% | 46.7% | -1.1% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 591 | 47.4% | -0.37% | 46.6% | -0.22% | 46.6% | 0.07% |
| tier2 | 571 | 41.0% | -0.6% | 43.9% | -0.23% | 46.3% | 1.41% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 721 | 45.6% | -1.18% | 45.9% | -0.76% |
| 90-94 | 279 | 46.5% | 3.39% | 47.6% | 5.09% |
| 85-89 | 162 | 41.2% | -2.14% | 46.9% | -0.15% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 146.69 | +131.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 145.62 | +131.3% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 143.97 | +126.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 135.61 | +123.9% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 143.77 | +123.0% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 143.77 | +123.0% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |
| SNDK | 07-10 | 🌀 Coil | 100.0 | 1915.92 | 1212.21 | -36.7% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| BRUN | 07-03 | 📐 Tight | 98.0 | 32.31 | 21.15 | -34.5% |
| BRUN | 07-06 | 📐 Tight | 98.0 | 32.31 | 21.15 | -34.5% |
| SNDK | 07-09 | 🌀 Coil | 100.0 | 1858.27 | 1258.58 | -32.3% |
| CRDO | 08-11 | 📐 Tight | 92.7 | 247.69 | 167.92 | -32.2% |
| CIFR | 07-31 | 📐 Tight | 97.3 | 22.32 | 15.17 | -32.0% |
| FCEL | 08-05 | 🌀 Coil | 99.1 | 21.14 | 14.40 | -31.9% |
| FCEL | 08-15 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
