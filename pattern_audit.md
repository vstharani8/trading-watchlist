# Pattern Performance Audit — 2026-08-15

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1034. With forward data: 1017.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 565 | 43.8% | -1.56% | 41.1% | -2.15% | 41.2% | -3.69% |
| 🌀 Coil | 376 | 47.4% | -0.68% | 43.8% | -1.28% | 42.7% | -4.74% |
| 📍 Near | 76 | 30.3% | -4.21% | 44.7% | -4.59% | 39.5% | -5.78% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 518 | 45.4% | -1.27% | 42.8% | -1.6% | 42.2% | -4.15% |
| tier2 | 499 | 42.7% | -1.62% | 41.8% | -2.45% | 41.0% | -4.32% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 638 | 41.9% | -2.21% | 40.8% | -4.59% |
| 90-94 | 256 | 46.2% | -0.75% | 45.3% | -2.51% |
| 85-89 | 123 | 36.9% | -3.59% | 38.5% | -5.86% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| DFTX | 06-09 | 📐 Tight | 94.3 | 22.95 | 48.45 | +111.1% |
| DFTX | 06-08 | 📐 Tight | 95.1 | 23.02 | 45.32 | +96.9% |
| DFTX | 06-11 | 📐 Tight | 94.9 | 24.11 | 43.65 | +81.0% |
| DFTX | 06-04 | 📐 Tight | 93.9 | 24.59 | 44.33 | +80.3% |
| FSLY | 07-23 | 📐 Tight | 95.6 | 19.43 | 29.93 | +54.0% |
| FSLY | 07-27 | 📐 Tight | 95.9 | 20.04 | 29.93 | +49.4% |
| RLAY | 06-10 | 📐 Tight | 97.1 | 13.49 | 20.00 | +48.3% |
| FSLY | 07-16 | 📐 Tight | 95.2 | 20.32 | 30.02 | +47.7% |
| UMAC | 08-03 | 🌀 Coil | 94.0 | 23.08 | 34.06 | +47.6% |
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
