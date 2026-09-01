# Pattern Performance Audit — 2026-09-01

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1202. With forward data: 1186.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 648 | 42.1% | -1.52% | 36.4% | -2.32% | 32.2% | -4.37% |
| 🌀 Coil | 441 | 43.0% | 0.26% | 36.9% | -1.14% | 33.1% | -4.91% |
| 📍 Near | 97 | 33.0% | -3.24% | 41.5% | -4.04% | 39.4% | -4.74% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 603 | 43.5% | -1.36% | 36.9% | -2.36% | 32.3% | -5.65% |
| tier2 | 583 | 39.8% | -0.64% | 37.0% | -1.68% | 33.9% | -3.52% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 749 | 36.0% | -3.15% | 30.4% | -6.5% |
| 90-94 | 289 | 39.9% | 1.67% | 38.4% | 0.87% |
| 85-89 | 148 | 36.6% | -3.5% | 36.6% | -5.54% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.34 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.34 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.34 | +134.6% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 140.34 | +131.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 140.34 | +122.9% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 140.34 | +121.6% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 140.34 | +120.5% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 140.34 | +120.4% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 140.34 | +117.7% |

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
