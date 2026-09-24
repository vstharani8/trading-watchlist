# Pattern Performance Audit — 2026-09-24

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1188. With forward data: 1170.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 631 | 42.7% | -1.67% | 45.2% | -0.94% | 45.8% | 0.06% |
| 🌀 Coil | 436 | 46.2% | 0.67% | 44.0% | 0.43% | 47.4% | -0.12% |
| 📍 Near | 103 | 36.3% | -3.13% | 38.2% | -4.72% | 46.1% | -2.03% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 598 | 47.0% | -0.75% | 45.3% | -0.62% | 46.8% | -0.86% |
| tier2 | 572 | 39.7% | -1.15% | 42.9% | -0.94% | 46.0% | 0.51% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 718 | 44.3% | -1.77% | 45.7% | -1.52% |
| 90-94 | 287 | 44.9% | 2.88% | 47.4% | 3.85% |
| 85-89 | 165 | 42.0% | -2.69% | 47.8% | -1.22% |

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
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| BTDR | 06-30 | 🌀 Coil | 87.8 | 15.87 | 8.90 | -43.9% |
| COHR | 06-30 | 📐 Tight | 96.7 | 394.47 | 222.05 | -43.7% |
| GFS | 06-30 | 📐 Tight | 94.3 | 82.41 | 47.07 | -42.9% |
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |
| SEI | 06-29 | 📐 Tight | 92.7 | 79.11 | 47.22 | -40.3% |
| WULF | 06-30 | 📐 Tight | 98.0 | 24.70 | 15.09 | -38.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
