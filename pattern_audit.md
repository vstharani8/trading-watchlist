# Pattern Performance Audit — 2026-08-19

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1091. With forward data: 1071.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 582 | 42.9% | -1.77% | 39.8% | -2.68% | 38.9% | -4.48% |
| 🌀 Coil | 413 | 41.4% | -1.14% | 36.9% | -2.07% | 34.7% | -5.82% |
| 📍 Near | 76 | 30.3% | -4.29% | 42.1% | -4.98% | 38.2% | -6.6% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 544 | 43.7% | -1.42% | 39.6% | -2.07% | 37.7% | -5.26% |
| tier2 | 527 | 39.1% | -2.01% | 38.1% | -3.16% | 36.8% | -5.03% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 667 | 39.5% | -2.64% | 36.9% | -5.72% |
| 90-94 | 273 | 39.2% | -1.87% | 38.4% | -3.22% |
| 85-89 | 131 | 34.6% | -4.01% | 36.2% | -6.22% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| DFTX | 06-09 | 📐 Tight | 94.3 | 22.95 | 48.45 | +111.1% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 35.11 | +98.4% |
| DFTX | 06-08 | 📐 Tight | 95.1 | 23.02 | 45.32 | +96.9% |
| DFTX | 06-11 | 📐 Tight | 94.9 | 24.11 | 43.65 | +81.0% |
| DFTX | 06-04 | 📐 Tight | 93.9 | 24.59 | 44.33 | +80.3% |
| AMLX | 07-28 | 📐 Tight | 91.0 | 19.55 | 35.11 | +79.6% |
| AMLX | 07-29 | 📐 Tight | 93.2 | 19.73 | 35.11 | +78.0% |
| RLAY | 06-10 | 📐 Tight | 97.1 | 13.49 | 20.00 | +48.3% |
| FSLY | 07-16 | 📐 Tight | 95.2 | 20.32 | 30.02 | +47.7% |
| RLAY | 06-09 | 📐 Tight | 96.7 | 14.09 | 20.75 | +47.3% |

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
