# Pattern Performance Audit — 2026-08-28

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1192. With forward data: 1177.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 648 | 44.1% | -1.36% | 39.6% | -1.66% | 37.9% | -3.06% |
| 🌀 Coil | 432 | 43.1% | 0.15% | 39.5% | -0.36% | 39.5% | -3.18% |
| 📍 Near | 97 | 34.0% | -3.15% | 45.7% | -3.42% | 42.6% | -4.65% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 593 | 44.4% | -1.38% | 39.6% | -1.77% | 38.3% | -4.35% |
| tier2 | 584 | 41.3% | -0.52% | 40.5% | -0.88% | 39.4% | -2.1% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 743 | 39.8% | -2.39% | 37.4% | -4.94% |
| 90-94 | 286 | 41.8% | 2.3% | 42.8% | 2.07% |
| 85-89 | 148 | 38.2% | -3.09% | 38.2% | -5.02% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 142.77 | +138.7% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 142.77 | +138.7% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 142.77 | +138.7% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 142.77 | +135.7% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 142.77 | +126.8% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 142.77 | +125.5% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 142.77 | +124.3% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 142.77 | +124.2% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 142.77 | +121.5% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 142.77 | +121.5% |

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
