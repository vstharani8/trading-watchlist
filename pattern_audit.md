# Pattern Performance Audit — 2026-09-07

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1189. With forward data: 1172.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 638 | 41.6% | -1.61% | 36.9% | -2.62% | 35.0% | -3.87% |
| 🌀 Coil | 437 | 43.8% | 0.14% | 37.0% | -1.54% | 36.1% | -4.79% |
| 📍 Near | 97 | 35.1% | -3.25% | 44.7% | -4.42% | 44.7% | -3.97% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 595 | 44.2% | -1.4% | 37.5% | -2.78% | 35.7% | -5.42% |
| tier2 | 577 | 39.4% | -0.77% | 37.7% | -1.93% | 36.8% | -2.98% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 739 | 37.8% | -3.35% | 36.2% | -5.85% |
| 90-94 | 285 | 38.4% | 0.99% | 37.0% | 0.32% |
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
