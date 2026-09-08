# Pattern Performance Audit — 2026-09-08

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1186. With forward data: 1152.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 629 | 40.9% | -1.78% | 36.7% | -2.75% | 35.1% | -3.92% |
| 🌀 Coil | 428 | 42.8% | -0.06% | 36.2% | -1.88% | 35.7% | -4.87% |
| 📍 Near | 95 | 33.7% | -3.97% | 43.5% | -5.09% | 44.6% | -4.12% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 585 | 43.4% | -1.6% | 36.8% | -3.11% | 35.2% | -5.58% |
| tier2 | 567 | 38.5% | -1.03% | 37.3% | -2.1% | 36.9% | -2.95% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 723 | 36.8% | -3.77% | 35.7% | -6.05% |
| 90-94 | 281 | 38.6% | 1.04% | 37.5% | 0.52% |
| 85-89 | 148 | 34.9% | -3.92% | 34.9% | -4.84% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 145.55 | +143.3% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 145.55 | +143.3% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 145.55 | +143.3% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 145.55 | +140.3% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 145.55 | +131.2% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 145.55 | +129.9% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 145.55 | +128.7% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 145.55 | +128.6% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 145.55 | +125.8% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 145.55 | +125.8% |

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
