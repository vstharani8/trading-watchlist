# Pattern Performance Audit — 2026-08-20

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1106. With forward data: 1091.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 596 | 43.1% | -1.53% | 39.0% | -1.27% | 36.8% | -3.18% |
| 🌀 Coil | 415 | 42.5% | 0.71% | 37.1% | -0.16% | 34.2% | -4.04% |
| 📍 Near | 80 | 30.3% | -4.29% | 42.1% | -4.89% | 38.2% | -6.62% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 554 | 43.6% | -1.52% | 38.3% | -1.96% | 35.2% | -5.42% |
| tier2 | 537 | 40.2% | -0.19% | 38.7% | -0.22% | 36.6% | -2.04% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 678 | 38.3% | -2.76% | 34.8% | -6.14% |
| 90-94 | 279 | 40.7% | 4.21% | 38.5% | 2.98% |
| 85-89 | 134 | 35.1% | -3.73% | 35.9% | -5.69% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 174.38 | +191.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 174.38 | +191.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 174.38 | +191.6% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 174.38 | +187.9% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 174.38 | +177.0% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 174.38 | +175.4% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 174.38 | +174.0% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 174.38 | +173.9% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 174.38 | +170.5% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 174.38 | +170.5% |

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
