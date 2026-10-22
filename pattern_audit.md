# Pattern Performance Audit — 2026-10-22

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 948. With forward data: 948.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 498 | 53.0% | 0.86% | 51.2% | 1.03% | 43.4% | -0.25% |
| 🌀 Coil | 370 | 51.9% | 2.18% | 52.7% | 2.48% | 45.4% | 0.32% |
| 📍 Near | 80 | 47.5% | -0.28% | 41.2% | -3.26% | 38.8% | -4.24% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 487 | 55.9% | 1.25% | 54.0% | 1.66% | 46.8% | 0.43% |
| tier2 | 461 | 48.2% | 1.3% | 47.7% | 0.78% | 40.6% | -1.2% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 574 | 51.4% | 0.15% | 42.3% | -2.16% |
| 90-94 | 233 | 54.1% | 5.33% | 48.9% | 4.03% |
| 85-89 | 141 | 44.0% | -1.12% | 41.1% | -0.33% |

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
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 136.62 | +114.6% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.46 | -47.7% |
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 12.40 | -40.0% |
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 61.99 | -38.5% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 61.99 | -37.8% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 61.99 | -37.1% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 61.99 | -36.4% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| AEHR | 09-21 | 📐 Tight | 97.6 | 96.93 | 63.33 | -34.7% |
| CGEM | 09-21 | 🌀 Coil | 98.1 | 21.35 | 13.98 | -34.5% |
| UMAC | 09-30 | 🌀 Coil | 94.7 | 24.48 | 16.38 | -33.1% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
