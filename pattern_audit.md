# Pattern Performance Audit — 2026-08-27

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1178. With forward data: 1161.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 642 | 44.3% | -1.45% | 39.4% | -1.84% | 37.4% | -3.41% |
| 🌀 Coil | 425 | 42.8% | 0.03% | 38.7% | -0.6% | 36.1% | -4.23% |
| 📍 Near | 94 | 31.5% | -3.66% | 41.3% | -4.17% | 38.0% | -5.54% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 583 | 44.2% | -1.51% | 39.1% | -2.08% | 36.1% | -5.31% |
| tier2 | 578 | 41.3% | -0.65% | 39.5% | -1.07% | 37.8% | -2.46% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 732 | 39.9% | -2.57% | 37.8% | -5.39% |
| 90-94 | 285 | 39.6% | 2.11% | 36.0% | 1.06% |
| 85-89 | 144 | 35.9% | -3.86% | 34.5% | -6.05% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 149.66 | +150.2% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 149.66 | +150.2% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 149.66 | +150.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 149.66 | +147.1% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 149.66 | +137.7% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 149.66 | +136.4% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 149.66 | +135.1% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 149.66 | +135.1% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 149.66 | +132.2% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 149.66 | +132.2% |

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
