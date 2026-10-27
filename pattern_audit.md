# Pattern Performance Audit — 2026-10-27

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 903. With forward data: 903.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 475 | 51.4% | 0.51% | 49.7% | 0.53% | 44.2% | -0.65% |
| 🌀 Coil | 350 | 50.0% | 1.77% | 52.0% | 2.15% | 42.9% | -0.23% |
| 📍 Near | 78 | 47.4% | -0.23% | 41.0% | -3.3% | 41.0% | -3.81% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 458 | 53.7% | 0.66% | 52.8% | 1.02% | 45.2% | 0.02% |
| tier2 | 445 | 47.2% | 1.22% | 46.7% | 0.62% | 41.6% | -1.56% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 543 | 50.8% | -0.17% | 41.8% | -2.82% |
| 90-94 | 221 | 51.6% | 4.6% | 46.2% | 3.15% |
| 85-89 | 139 | 43.2% | -1.3% | 45.3% | 1.08% |

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
| QURE | 09-03 | 📐 Tight | 99.1 | 44.86 | 23.46 | -47.7% |
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 11.46 | -44.5% |
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 56.60 | -43.8% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 56.60 | -43.2% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 55.65 | -42.9% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 56.60 | -42.5% |
| NBIS | 10-06 | 📐 Tight | 93.2 | 249.87 | 153.27 | -38.7% |
| NBIS | 10-02 | 📐 Tight | 95.6 | 242.81 | 153.27 | -36.9% |
| FCEL | 10-05 | 🌀 Coil | 95.3 | 18.07 | 11.46 | -36.6% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
