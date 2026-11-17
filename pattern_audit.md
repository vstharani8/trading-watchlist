# Pattern Performance Audit — 2026-11-17

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 586. With forward data: 586.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 315 | 48.9% | 0.22% | 52.1% | -0.35% | 49.8% | -1.23% |
| 🌀 Coil | 204 | 53.9% | 0.39% | 62.3% | 1.88% | 47.5% | -0.16% |
| 📍 Near | 67 | 43.3% | -1.04% | 38.8% | -3.95% | 38.8% | -4.94% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier2 | 294 | 45.9% | -0.53% | 49.0% | -1.61% | 43.5% | -4.06% |
| tier1 | 292 | 54.1% | 0.81% | 59.2% | 1.65% | 52.1% | 1.51% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 349 | 55.9% | 0.19% | 46.4% | -2.31% |
| 90-94 | 130 | 56.9% | 0.28% | 51.5% | -1.4% |
| 85-89 | 107 | 44.9% | -0.9% | 47.7% | 2.21% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| P | 09-10 | 🌀 Coil | 87.7 | 94.10 | 150.57 | +60.0% |
| P | 09-09 | 🌀 Coil | 89.3 | 97.06 | 152.66 | +57.3% |
| TXG | 09-04 | 📍 Near | 99.5 | 62.65 | 97.74 | +56.0% |
| REPL | 10-06 | 📐 Tight | 96.4 | 13.25 | 20.65 | +55.9% |
| FIGS | 09-28 | 📐 Tight | 85.1 | 13.62 | 20.83 | +52.9% |
| NTSK | 09-30 | 📍 Near | 90.5 | 17.44 | 26.52 | +52.1% |
| OKTA | 08-24 | 🌀 Coil | 89.9 | 130.97 | 196.62 | +50.1% |
| NTSK | 10-01 | 📍 Near | 90.3 | 17.85 | 26.19 | +46.7% |
| FIGS | 09-29 | 📐 Tight | 88.7 | 14.06 | 20.48 | +45.7% |
| P | 09-07 | 🌀 Coil | 87.5 | 101.14 | 147.20 | +45.5% |

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
