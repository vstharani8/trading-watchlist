# Pattern Performance Audit — 2026-10-02

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1200. With forward data: 1180.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 627 | 48.7% | -0.3% | 53.4% | 1.11% | 55.7% | 3.07% |
| 🌀 Coil | 441 | 47.2% | 0.9% | 47.5% | 1.25% | 50.5% | 1.45% |
| 📍 Near | 112 | 40.7% | -2.44% | 43.5% | -3.12% | 51.9% | -0.18% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 599 | 50.3% | -0.01% | 50.3% | 0.62% | 51.8% | 1.39% |
| tier2 | 581 | 44.5% | -0.09% | 50.3% | 0.91% | 55.0% | 2.96% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 734 | 51.4% | -0.02% | 52.9% | 0.88% |
| 90-94 | 279 | 50.5% | 4.04% | 56.0% | 6.25% |
| 85-89 | 167 | 44.8% | -1.26% | 50.9% | 0.94% |

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
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.37 | -47.9% |
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |
| SNDK | 07-10 | 🌀 Coil | 100.0 | 1915.92 | 1212.21 | -36.7% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| BRUN | 07-06 | 📐 Tight | 98.0 | 32.31 | 21.15 | -34.5% |
| SNDK | 07-09 | 🌀 Coil | 100.0 | 1858.27 | 1258.58 | -32.3% |
| CRDO | 08-11 | 📐 Tight | 92.7 | 247.69 | 167.92 | -32.2% |
| CIFR | 07-31 | 📐 Tight | 97.3 | 22.32 | 15.17 | -32.0% |
| CGEM | 09-21 | 🌀 Coil | 98.1 | 21.35 | 14.53 | -31.9% |
| FCEL | 08-05 | 🌀 Coil | 99.1 | 21.14 | 14.40 | -31.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
