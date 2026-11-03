# Pattern Performance Audit — 2026-11-03

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 815. With forward data: 815.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 427 | 50.6% | 0.51% | 47.3% | 0.15% | 46.4% | -0.46% |
| 🌀 Coil | 314 | 48.4% | 1.71% | 50.3% | 1.93% | 40.8% | -0.41% |
| 📍 Near | 74 | 45.9% | -0.3% | 39.2% | -3.89% | 40.5% | -4.58% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 408 | 52.7% | 0.57% | 51.0% | 0.64% | 45.6% | 0.06% |
| tier2 | 407 | 45.9% | 1.23% | 44.5% | 0.31% | 41.8% | -1.69% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 481 | 48.9% | -0.69% | 42.4% | -2.88% |
| 90-94 | 203 | 49.8% | 4.62% | 44.8% | 2.74% |
| 85-89 | 131 | 40.5% | -1.7% | 46.6% | 1.24% |

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
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 10.50 | -49.1% |
| INTC | 10-05 | 📍 Near | 98.5 | 116.19 | 59.97 | -48.4% |
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.46 | -47.7% |
| INTC | 10-06 | 📍 Near | 97.5 | 112.50 | 59.97 | -46.7% |
| NBIS | 10-06 | 📐 Tight | 93.2 | 249.87 | 141.39 | -43.4% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 55.65 | -42.9% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 56.60 | -42.5% |
| TTMI | 10-06 | 📐 Tight | 89.2 | 132.71 | 76.58 | -42.3% |
| FCEL | 10-05 | 🌀 Coil | 95.3 | 18.07 | 10.50 | -41.9% |
| NBIS | 10-05 | 📐 Tight | 95.7 | 232.57 | 141.39 | -39.2% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
