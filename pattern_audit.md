# Pattern Performance Audit — 2026-10-20

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 986. With forward data: 986.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 524 | 52.7% | 0.69% | 51.0% | 1.0% | 43.1% | -0.34% |
| 🌀 Coil | 381 | 51.4% | 2.06% | 52.5% | 2.42% | 44.6% | 0.14% |
| 📍 Near | 81 | 48.1% | -0.26% | 42.0% | -3.05% | 39.5% | -4.12% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 505 | 55.0% | 1.12% | 53.9% | 1.63% | 46.3% | 0.25% |
| tier2 | 481 | 48.4% | 1.16% | 47.6% | 0.77% | 40.3% | -1.21% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 600 | 51.0% | 0.09% | 42.5% | -2.11% |
| 90-94 | 242 | 55.0% | 5.41% | 48.3% | 3.95% |
| 85-89 | 144 | 43.1% | -1.14% | 38.9% | -1.01% |

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
| FCEL | 10-06 | 🌀 Coil | 95.1 | 20.65 | 12.89 | -37.6% |
| AEHR | 09-29 | 📐 Tight | 98.4 | 100.78 | 63.33 | -37.2% |
| AEHR | 09-30 | 📐 Tight | 98.6 | 99.62 | 63.33 | -36.4% |
| CIFR | 08-03 | 📐 Tight | 97.3 | 24.16 | 15.50 | -35.8% |
| AEHR | 09-28 | 📐 Tight | 98.6 | 98.49 | 63.33 | -35.7% |
| AEHR | 09-24 | 🌀 Coil | 98.1 | 97.42 | 63.33 | -35.0% |
| AEHR | 09-21 | 📐 Tight | 97.6 | 96.93 | 63.33 | -34.7% |
| CGEM | 09-21 | 🌀 Coil | 98.1 | 21.35 | 13.98 | -34.5% |
| OUST | 09-25 | 📐 Tight | 89.7 | 43.72 | 28.86 | -34.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
