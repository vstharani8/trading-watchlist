# Pattern Performance Audit — 2026-08-26

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1162. With forward data: 1147.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 634 | 43.0% | -1.54% | 37.9% | -1.95% | 35.0% | -3.56% |
| 🌀 Coil | 421 | 41.9% | -0.05% | 36.4% | -0.78% | 32.3% | -4.73% |
| 📍 Near | 92 | 32.6% | -3.94% | 42.7% | -4.47% | 39.3% | -5.93% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier2 | 574 | 40.2% | -0.76% | 38.2% | -1.11% | 35.4% | -2.55% |
| tier1 | 573 | 43.3% | -1.6% | 37.1% | -2.32% | 33.3% | -5.8% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 722 | 38.2% | -2.85% | 34.1% | -5.96% |
| 90-94 | 283 | 39.2% | 2.24% | 36.4% | 1.23% |
| 85-89 | 142 | 32.1% | -3.98% | 31.4% | -6.08% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 158.83 | +165.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 158.83 | +165.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 158.83 | +165.6% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 158.83 | +162.2% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 158.83 | +152.3% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 158.83 | +150.8% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 158.83 | +149.5% |
| MRNA | 08-12 | 🌀 Coil | 92.7 | 63.67 | 158.83 | +149.5% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 158.83 | +146.4% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 158.83 | +146.4% |

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
