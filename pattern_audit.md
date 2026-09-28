# Pattern Performance Audit — 2026-09-28

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1182. With forward data: 1163.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 618 | 44.8% | -0.95% | 47.1% | -0.28% | 47.8% | 1.26% |
| 🌀 Coil | 438 | 45.6% | 0.68% | 43.6% | 0.25% | 45.6% | 0.06% |
| 📍 Near | 107 | 38.8% | -2.72% | 40.8% | -4.05% | 49.5% | -0.82% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 592 | 47.4% | -0.41% | 46.2% | -0.42% | 47.1% | -0.15% |
| tier2 | 571 | 41.6% | -0.57% | 44.1% | -0.42% | 47.2% | 1.42% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 718 | 45.3% | -1.37% | 46.0% | -0.81% |
| 90-94 | 281 | 46.4% | 2.94% | 49.6% | 4.6% |
| 85-89 | 164 | 42.8% | -2.11% | 47.8% | -0.03% |

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
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |
| SNDK | 07-10 | 🌀 Coil | 100.0 | 1915.92 | 1212.21 | -36.7% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| TTMI | 07-01 | 📐 Tight | 97.5 | 179.70 | 115.51 | -35.7% |
| GFS | 07-01 | 📐 Tight | 94.2 | 77.04 | 49.77 | -35.4% |
| BRUN | 07-03 | 📐 Tight | 98.0 | 32.31 | 21.15 | -34.5% |
| BRUN | 07-06 | 📐 Tight | 98.0 | 32.31 | 21.15 | -34.5% |
| VSH | 07-01 | 📐 Tight | 98.2 | 51.05 | 33.68 | -34.0% |
| COHR | 07-01 | 📐 Tight | 96.5 | 368.65 | 249.06 | -32.4% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
