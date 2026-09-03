# Pattern Performance Audit — 2026-09-03

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1194. With forward data: 1178.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 643 | 42.7% | -1.53% | 35.8% | -2.58% | 31.2% | -4.55% |
| 🌀 Coil | 438 | 41.6% | -0.18% | 35.3% | -2.07% | 31.9% | -5.62% |
| 📍 Near | 97 | 34.7% | -3.08% | 42.1% | -4.56% | 42.1% | -4.58% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 600 | 43.1% | -1.63% | 35.5% | -3.04% | 31.0% | -6.22% |
| tier2 | 578 | 40.1% | -0.65% | 36.8% | -2.03% | 33.8% | -3.63% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 744 | 36.5% | -3.5% | 31.4% | -6.67% |
| 90-94 | 286 | 38.5% | 0.99% | 36.0% | 0.02% |
| 85-89 | 148 | 29.9% | -4.64% | 29.9% | -5.97% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 150.81 | +152.2% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 150.81 | +152.2% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 150.81 | +152.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 150.81 | +149.0% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 150.81 | +139.5% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 150.81 | +138.2% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 150.81 | +136.9% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 150.81 | +136.9% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 150.81 | +134.0% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 150.81 | +134.0% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| NVTS | 06-17 | 🌀 Coil | 97.5 | 22.34 | 11.46 | -48.7% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| NVTS | 06-16 | 🌀 Coil | 97.5 | 22.09 | 11.76 | -46.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |
| NVTS | 06-12 | 📐 Tight | 96.8 | 23.39 | 13.09 | -44.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
