# Pattern Performance Audit — 2026-10-19

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1006. With forward data: 1006.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 535 | 52.5% | 0.54% | 50.8% | 0.98% | 43.0% | -0.47% |
| 🌀 Coil | 386 | 50.8% | 1.83% | 51.8% | 2.33% | 43.8% | -0.24% |
| 📍 Near | 85 | 47.1% | -1.07% | 41.2% | -3.26% | 40.0% | -4.61% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 515 | 54.6% | 0.91% | 53.2% | 1.55% | 45.6% | -0.11% |
| tier2 | 491 | 48.1% | 0.89% | 47.5% | 0.71% | 40.3% | -1.39% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 614 | 50.5% | 0.01% | 42.3% | -2.38% |
| 90-94 | 245 | 54.7% | 5.39% | 47.3% | 3.45% |
| 85-89 | 147 | 42.9% | -1.21% | 38.8% | -0.82% |

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
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 60.60 | -39.9% |
| CGEM | 09-21 | 🌀 Coil | 98.1 | 21.35 | 12.93 | -39.4% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 60.60 | -39.2% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 60.60 | -38.5% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 60.60 | -37.8% |
| AEHR | 09-21 | 📐 Tight | 97.6 | 96.93 | 60.60 | -37.5% |
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 13.00 | -37.0% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| AXTI | 09-21 | 🌀 Coil | 99.9 | 79.93 | 51.47 | -35.6% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
