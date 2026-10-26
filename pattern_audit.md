# Pattern Performance Audit — 2026-10-26

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 915. With forward data: 915.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 481 | 52.0% | 0.65% | 50.3% | 0.71% | 44.1% | -0.73% |
| 🌀 Coil | 356 | 50.6% | 1.94% | 52.2% | 2.35% | 43.3% | -0.22% |
| 📍 Near | 78 | 47.4% | -0.23% | 41.0% | -3.3% | 41.0% | -4.37% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 468 | 54.5% | 0.91% | 53.4% | 1.33% | 45.3% | -0.02% |
| tier2 | 447 | 47.4% | 1.25% | 47.0% | 0.67% | 41.6% | -1.7% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 551 | 51.2% | 0.05% | 41.9% | -2.91% |
| 90-94 | 224 | 52.2% | 4.76% | 46.4% | 3.38% |
| 85-89 | 140 | 43.6% | -1.22% | 45.0% | 0.56% |

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
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 11.11 | -46.2% |
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 55.31 | -45.1% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 55.31 | -44.5% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 55.31 | -43.8% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 55.65 | -42.9% |
| TTMI | 10-06 | 📐 Tight | 89.2 | 132.71 | 80.11 | -39.6% |
| FCEL | 10-05 | 🌀 Coil | 95.3 | 18.07 | 11.11 | -38.5% |
| COHR | 10-02 | 🌀 Coil | 94.7 | 337.04 | 209.29 | -37.9% |
| NBIS | 10-06 | 📐 Tight | 93.2 | 249.87 | 158.74 | -36.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
