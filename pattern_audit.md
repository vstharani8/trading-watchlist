# Pattern Performance Audit — 2026-11-11

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 679. With forward data: 679.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 351 | 47.9% | 0.27% | 49.9% | -0.57% | 48.7% | -1.23% |
| 🌀 Coil | 257 | 46.7% | 0.36% | 51.8% | 0.95% | 42.0% | -0.84% |
| 📍 Near | 71 | 43.7% | -0.83% | 39.4% | -4.13% | 40.8% | -4.59% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier2 | 341 | 44.3% | 0.38% | 46.3% | -1.0% | 42.5% | -3.17% |
| tier1 | 338 | 49.7% | 0.0% | 52.7% | 0.27% | 48.2% | 0.32% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 398 | 51.0% | -0.89% | 43.2% | -3.19% |
| 90-94 | 162 | 51.2% | 1.83% | 48.8% | 0.68% |
| 85-89 | 119 | 42.0% | -1.62% | 47.9% | 1.57% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 146.69 | +131.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 145.62 | +131.3% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 143.77 | +123.0% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 143.77 | +123.0% |
| P | 09-10 | 🌀 Coil | 87.7 | 94.10 | 150.57 | +60.0% |
| P | 09-09 | 🌀 Coil | 89.3 | 97.06 | 152.66 | +57.3% |
| TXG | 09-04 | 📍 Near | 99.5 | 62.65 | 97.74 | +56.0% |
| REPL | 10-06 | 📐 Tight | 96.4 | 13.25 | 20.65 | +55.9% |
| FIGS | 09-28 | 📐 Tight | 85.1 | 13.62 | 20.83 | +52.9% |
| NTSK | 09-30 | 📍 Near | 90.5 | 17.44 | 26.52 | +52.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| INTC | 10-05 | 📍 Near | 98.5 | 116.19 | 59.97 | -48.4% |
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.46 | -47.7% |
| INTC | 10-06 | 📍 Near | 97.5 | 112.50 | 60.55 | -46.2% |
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 11.21 | -45.7% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 55.65 | -42.9% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 56.60 | -42.5% |
| FCEL | 10-05 | 🌀 Coil | 95.3 | 18.07 | 10.50 | -41.9% |
| NBIS | 10-06 | 📐 Tight | 93.2 | 249.87 | 151.64 | -39.3% |
| NBIS | 10-05 | 📐 Tight | 95.7 | 232.57 | 141.39 | -39.2% |
| TTMI | 10-06 | 📐 Tight | 89.2 | 132.71 | 81.63 | -38.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
