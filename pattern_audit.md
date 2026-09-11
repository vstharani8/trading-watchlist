# Pattern Performance Audit — 2026-09-11

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1205. With forward data: 1185.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 640 | 39.1% | -2.17% | 36.2% | -2.8% | 35.1% | -3.76% |
| 🌀 Coil | 442 | 40.9% | -0.61% | 35.8% | -2.11% | 37.2% | -4.59% |
| 📍 Near | 103 | 29.7% | -4.14% | 38.6% | -5.38% | 41.6% | -4.34% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 604 | 42.0% | -1.88% | 36.8% | -3.32% | 36.0% | -5.43% |
| tier2 | 581 | 35.7% | -1.64% | 35.7% | -2.18% | 37.0% | -2.75% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 737 | 36.8% | -3.72% | 37.2% | -5.38% |
| 90-94 | 286 | 37.4% | 0.68% | 37.4% | 0.06% |
| 85-89 | 162 | 31.8% | -4.53% | 31.2% | -5.76% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 135.61 | +123.9% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 136.62 | +117.0% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 136.62 | +115.8% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 136.62 | +114.6% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 136.62 | +114.6% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 136.62 | +112.0% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| NVTS | 06-17 | 🌀 Coil | 97.5 | 22.34 | 11.46 | -48.7% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| NVTS | 06-16 | 🌀 Coil | 97.5 | 22.09 | 11.76 | -46.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |
| BTDR | 06-30 | 🌀 Coil | 87.8 | 15.87 | 8.90 | -43.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
