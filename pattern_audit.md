# Pattern Performance Audit — 2026-11-05

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 795. With forward data: 795.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 420 | 50.0% | 0.45% | 47.1% | 0.15% | 46.7% | -0.3% |
| 🌀 Coil | 302 | 47.4% | 1.58% | 50.7% | 1.9% | 40.7% | -0.48% |
| 📍 Near | 73 | 45.2% | -0.68% | 38.4% | -4.49% | 39.7% | -5.09% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 398 | 52.5% | 0.52% | 51.5% | 0.71% | 46.0% | 0.19% |
| tier2 | 397 | 44.6% | 1.03% | 43.8% | 0.06% | 41.6% | -1.8% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 470 | 48.7% | -0.85% | 42.1% | -2.93% |
| 90-94 | 198 | 50.0% | 4.87% | 46.5% | 3.17% |
| 85-89 | 127 | 40.2% | -2.04% | 45.7% | 0.83% |

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
