# Pattern Performance Audit — 2026-09-16

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1177. With forward data: 1161.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 636 | 37.8% | -2.54% | 35.4% | -3.21% | 35.2% | -3.3% |
| 🌀 Coil | 421 | 41.7% | -0.09% | 36.1% | -1.59% | 36.4% | -3.04% |
| 📍 Near | 104 | 34.0% | -4.04% | 36.9% | -6.19% | 40.8% | -4.74% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 590 | 42.5% | -1.6% | 36.5% | -2.83% | 34.8% | -4.13% |
| tier2 | 571 | 35.1% | -1.99% | 35.1% | -2.96% | 37.6% | -2.51% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 717 | 35.3% | -4.09% | 34.7% | -4.86% |
| 90-94 | 279 | 39.4% | 0.97% | 40.1% | 0.93% |
| 85-89 | 165 | 32.1% | -4.27% | 35.8% | -3.98% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 146.69 | +131.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 143.77 | +128.3% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 143.97 | +126.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 135.61 | +123.9% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 143.77 | +123.0% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 143.77 | +123.0% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |
| BTDR | 06-30 | 🌀 Coil | 87.8 | 15.87 | 8.90 | -43.9% |
| COHR | 06-30 | 📐 Tight | 96.7 | 394.47 | 222.05 | -43.7% |
| GFS | 06-30 | 📐 Tight | 94.3 | 82.41 | 47.07 | -42.9% |
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
