# Pattern Performance Audit — 2026-10-16

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1042. With forward data: 1042.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 550 | 52.0% | 0.48% | 52.0% | 1.5% | 46.2% | 1.31% |
| 🌀 Coil | 397 | 49.9% | 1.69% | 52.4% | 2.57% | 45.8% | 1.09% |
| 📍 Near | 95 | 45.3% | -1.29% | 45.3% | -2.26% | 46.3% | -1.99% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 531 | 53.7% | 0.81% | 53.9% | 1.94% | 48.0% | 1.32% |
| tier2 | 511 | 47.4% | 0.76% | 49.1% | 1.17% | 44.0% | 0.51% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 635 | 51.5% | 0.49% | 44.9% | -0.71% |
| 90-94 | 252 | 56.0% | 5.76% | 52.0% | 5.15% |
| 85-89 | 155 | 44.5% | -0.84% | 41.3% | 0.78% |

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
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.46 | -47.7% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| CGEM | 09-21 | 🌀 Coil | 98.1 | 21.35 | 14.00 | -34.4% |
| CRDO | 08-11 | 📐 Tight | 92.7 | 247.69 | 167.92 | -32.2% |
| CIFR | 07-31 | 📐 Tight | 97.3 | 22.32 | 15.17 | -32.0% |
| FCEL | 08-05 | 🌀 Coil | 99.1 | 21.14 | 14.40 | -31.9% |
| FCEL | 08-15 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |
| FCEL | 08-17 | 🌀 Coil | 99.0 | 22.36 | 15.25 | -31.8% |
| ALM | 09-07 | 📍 Near | 97.0 | 19.12 | 13.04 | -31.8% |
| ALM | 09-08 | 📍 Near | 97.0 | 19.12 | 13.04 | -31.8% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
