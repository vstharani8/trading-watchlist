# Pattern Performance Audit — 2026-10-05

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1179. With forward data: 1161.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 619 | 48.6% | -0.06% | 53.9% | 1.62% | 55.0% | 3.61% |
| 🌀 Coil | 432 | 47.1% | 0.96% | 48.7% | 1.64% | 51.3% | 2.01% |
| 📍 Near | 110 | 40.4% | -2.48% | 45.0% | -2.66% | 54.1% | 0.75% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 590 | 49.8% | 0.02% | 51.2% | 0.87% | 51.6% | 1.74% |
| tier2 | 571 | 44.6% | 0.17% | 51.0% | 1.58% | 55.6% | 3.77% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 723 | 51.1% | 0.27% | 51.3% | 1.33% |
| 90-94 | 276 | 53.0% | 4.63% | 58.5% | 6.78% |
| 85-89 | 162 | 48.1% | -0.32% | 55.0% | 2.17% |

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
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.46 | -47.7% |
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |
| SNDK | 07-10 | 🌀 Coil | 100.0 | 1915.92 | 1212.21 | -36.7% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| SNDK | 07-09 | 🌀 Coil | 100.0 | 1858.27 | 1258.58 | -32.3% |
| CRDO | 08-11 | 📐 Tight | 92.7 | 247.69 | 167.92 | -32.2% |
| CIFR | 07-31 | 📐 Tight | 97.3 | 22.32 | 15.17 | -32.0% |
| FCEL | 08-05 | 🌀 Coil | 99.1 | 21.14 | 14.40 | -31.9% |
| FCEL | 08-15 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |
| FCEL | 08-17 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
