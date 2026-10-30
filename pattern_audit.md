# Pattern Performance Audit — 2026-10-30

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 872. With forward data: 872.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 461 | 51.0% | 0.48% | 48.8% | 0.27% | 45.8% | 0.2% |
| 🌀 Coil | 335 | 49.0% | 1.73% | 51.0% | 1.9% | 41.5% | -0.32% |
| 📍 Near | 76 | 47.4% | 0.02% | 40.8% | -3.31% | 42.1% | -2.64% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 438 | 53.0% | 0.6% | 51.8% | 0.75% | 45.4% | 0.35% |
| tier2 | 434 | 46.8% | 1.24% | 46.1% | 0.42% | 42.2% | -0.84% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 520 | 50.2% | -0.43% | 42.5% | -2.18% |
| 90-94 | 215 | 50.2% | 4.36% | 45.1% | 3.09% |
| 85-89 | 137 | 42.3% | -1.5% | 46.7% | 1.88% |

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
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 55.65 | -42.9% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 56.60 | -42.5% |
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 12.18 | -41.0% |
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 63.95 | -36.5% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 64.54 | -35.2% |
| AEHR | 09-21 | 📐 Tight | 97.6 | 96.93 | 63.33 | -34.7% |
| NBIS | 09-24 | 🌀 Coil | 93.5 | 243.48 | 159.17 | -34.6% |
| CGEM | 09-21 | 🌀 Coil | 98.1 | 21.35 | 13.98 | -34.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
