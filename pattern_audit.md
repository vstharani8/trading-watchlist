# Pattern Performance Audit — 2026-10-23

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 948. With forward data: 948.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 498 | 53.0% | 0.86% | 51.2% | 1.03% | 44.4% | -0.48% |
| 🌀 Coil | 370 | 51.9% | 2.18% | 52.7% | 2.48% | 45.1% | 0.12% |
| 📍 Near | 80 | 47.5% | -0.28% | 41.2% | -3.26% | 38.8% | -4.44% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 487 | 55.9% | 1.25% | 54.0% | 1.66% | 46.8% | 0.27% |
| tier2 | 461 | 48.2% | 1.3% | 47.7% | 0.78% | 41.4% | -1.48% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 574 | 51.4% | 0.15% | 42.5% | -2.6% |
| 90-94 | 233 | 54.1% | 5.33% | 48.9% | 4.05% |
| 85-89 | 141 | 44.0% | -1.12% | 43.3% | 0.0% |

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
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 55.65 | -44.8% |
| TTMI | 10-06 | 📐 Tight | 89.2 | 132.71 | 73.89 | -44.3% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 55.65 | -44.1% |
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 11.58 | -43.9% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 55.65 | -43.5% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 55.65 | -42.9% |
| COHR | 10-02 | 🌀 Coil | 94.7 | 337.04 | 207.82 | -38.3% |
| NBIS | 10-06 | 📐 Tight | 93.2 | 249.87 | 159.17 | -36.3% |
| OUST | 09-25 | 📐 Tight | 89.7 | 43.72 | 27.98 | -36.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
