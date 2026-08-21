# Pattern Performance Audit — 2026-08-21

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1118. With forward data: 1106.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 608 | 43.1% | -1.68% | 38.9% | -2.02% | 35.9% | -4.1% |
| 🌀 Coil | 416 | 42.3% | -0.05% | 37.2% | -1.24% | 33.3% | -5.3% |
| 📍 Near | 82 | 30.0% | -4.08% | 41.2% | -4.69% | 37.5% | -6.4% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 559 | 43.4% | -1.58% | 37.8% | -2.38% | 34.0% | -6.04% |
| tier2 | 547 | 40.2% | -0.88% | 39.1% | -1.45% | 36.1% | -3.37% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 686 | 38.4% | -2.92% | 34.4% | -6.38% |
| 90-94 | 283 | 40.5% | 1.49% | 37.3% | 0.03% |
| 85-89 | 137 | 34.3% | -4.01% | 33.6% | -6.25% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 133.32 | +122.9% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 133.32 | +122.9% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 133.32 | +122.9% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 133.32 | +120.1% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 133.32 | +111.8% |
| DFTX | 06-09 | 📐 Tight | 94.3 | 22.95 | 48.45 | +111.1% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 133.32 | +110.5% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 133.32 | +109.5% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 133.32 | +109.4% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| NVTS | 06-17 | 🌀 Coil | 97.5 | 22.34 | 11.46 | -48.7% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| AXTI | 06-03 | 📍 Near | 100.0 | 106.70 | 56.62 | -46.9% |
| NVTS | 06-16 | 🌀 Coil | 97.5 | 22.09 | 11.76 | -46.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
