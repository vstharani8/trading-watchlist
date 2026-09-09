# Pattern Performance Audit — 2026-09-09

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1186. With forward data: 1166.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 638 | 41.3% | -1.85% | 39.0% | -2.53% | 37.9% | -3.37% |
| 🌀 Coil | 431 | 43.0% | -0.1% | 36.5% | -1.81% | 38.4% | -4.13% |
| 📍 Near | 97 | 32.6% | -3.7% | 43.2% | -4.68% | 45.3% | -3.21% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 595 | 43.7% | -1.59% | 38.3% | -3.07% | 38.3% | -5.11% |
| tier2 | 571 | 38.6% | -1.11% | 38.6% | -1.81% | 39.1% | -2.11% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 730 | 39.2% | -3.45% | 39.4% | -4.96% |
| 90-94 | 283 | 38.9% | 0.98% | 39.6% | 0.66% |
| 85-89 | 153 | 34.0% | -4.04% | 33.3% | -5.28% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 140.33 | +131.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 140.33 | +122.9% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 140.33 | +121.6% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 140.33 | +120.5% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 140.33 | +120.4% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 140.33 | +117.7% |

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
