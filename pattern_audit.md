# Pattern Performance Audit — 2026-09-04

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1212. With forward data: 1194.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 652 | 43.2% | -1.41% | 38.3% | -2.25% | 34.5% | -4.06% |
| 🌀 Coil | 443 | 43.6% | 0.14% | 37.0% | -1.57% | 34.2% | -5.33% |
| 📍 Near | 99 | 37.1% | -2.84% | 46.4% | -4.0% | 46.4% | -3.85% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 606 | 45.0% | -1.33% | 38.0% | -2.57% | 34.2% | -5.7% |
| tier2 | 588 | 40.7% | -0.55% | 38.9% | -1.7% | 36.7% | -3.29% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 755 | 38.6% | -3.11% | 34.1% | -6.32% |
| 90-94 | 290 | 39.2% | 1.24% | 37.8% | 0.36% |
| 85-89 | 149 | 36.5% | -3.8% | 37.2% | -4.89% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 148.87 | +148.9% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 148.87 | +148.9% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 148.87 | +148.9% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 148.87 | +145.8% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 148.87 | +136.4% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 148.87 | +135.1% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 148.87 | +133.9% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 148.87 | +133.8% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 148.87 | +130.9% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 148.87 | +130.9% |

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
