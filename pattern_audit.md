# Pattern Performance Audit — 2026-08-24

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1134. With forward data: 1118.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 615 | 43.3% | -1.51% | 38.7% | -1.69% | 36.0% | -3.28% |
| 🌀 Coil | 416 | 42.7% | 0.22% | 37.6% | -0.52% | 33.7% | -4.3% |
| 📍 Near | 87 | 32.9% | -3.91% | 43.9% | -4.31% | 40.2% | -5.83% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 561 | 43.4% | -1.51% | 38.0% | -2.05% | 34.2% | -5.32% |
| tier2 | 557 | 41.1% | -0.56% | 39.3% | -0.82% | 36.7% | -2.35% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 698 | 38.5% | -2.5% | 34.6% | -5.53% |
| 90-94 | 283 | 41.3% | 2.31% | 38.5% | 1.22% |
| 85-89 | 137 | 33.6% | -3.91% | 33.6% | -5.95% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 145.13 | +142.7% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 145.13 | +142.7% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 145.13 | +142.7% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 145.13 | +139.6% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 145.13 | +130.5% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 145.13 | +129.2% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 145.13 | +128.0% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 145.13 | +127.9% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 145.13 | +125.2% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 145.13 | +125.2% |

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
