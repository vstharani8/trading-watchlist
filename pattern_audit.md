# Pattern Performance Audit — 2026-10-07

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1162. With forward data: 1162.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 620 | 49.7% | 0.22% | 53.8% | 1.78% | 55.3% | 3.98% |
| 🌀 Coil | 430 | 48.8% | 1.26% | 50.0% | 1.87% | 52.6% | 2.65% |
| 📍 Near | 112 | 43.6% | -1.83% | 50.0% | -1.82% | 60.9% | 1.61% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 591 | 51.1% | 0.31% | 51.8% | 1.12% | 51.8% | 2.28% |
| tier2 | 571 | 46.3% | 0.51% | 52.2% | 1.83% | 57.9% | 4.27% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 717 | 51.8% | 0.45% | 52.7% | 1.66% |
| 90-94 | 282 | 54.3% | 4.84% | 60.1% | 7.33% |
| 85-89 | 163 | 48.7% | 0.13% | 55.1% | 3.28% |

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
| CRDO | 08-11 | 📐 Tight | 92.7 | 247.69 | 167.92 | -32.2% |
| CIFR | 07-31 | 📐 Tight | 97.3 | 22.32 | 15.17 | -32.0% |
| FCEL | 08-05 | 🌀 Coil | 99.1 | 21.14 | 14.40 | -31.9% |
| FCEL | 08-15 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |
| FCEL | 08-17 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |
| ALM | 09-07 | 📍 Near | 97.0 | 19.12 | 13.04 | -31.8% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
