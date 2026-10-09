# Pattern Performance Audit — 2026-10-09

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1142. With forward data: 1142.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 610 | 48.4% | 0.13% | 50.7% | 1.35% | 51.6% | 3.21% |
| 🌀 Coil | 422 | 49.1% | 1.47% | 50.0% | 1.99% | 49.5% | 2.08% |
| 📍 Near | 110 | 40.0% | -2.13% | 42.7% | -2.58% | 50.9% | 0.28% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 581 | 51.3% | 0.51% | 51.3% | 1.23% | 50.9% | 2.1% |
| tier2 | 561 | 44.2% | 0.3% | 48.0% | 1.19% | 50.6% | 2.93% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 701 | 49.8% | 0.31% | 49.6% | 1.13% |
| 90-94 | 278 | 51.4% | 4.43% | 54.0% | 6.17% |
| 85-89 | 163 | 46.0% | -0.44% | 50.3% | 2.19% |

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
| SEDG | 07-15 | 📐 Tight | 92.0 | 54.58 | 32.02 | -41.3% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
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
