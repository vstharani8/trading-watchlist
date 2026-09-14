# Pattern Performance Audit — 2026-09-14

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1185. With forward data: 1165.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 632 | 39.4% | -2.33% | 36.7% | -3.12% | 37.0% | -3.07% |
| 🌀 Coil | 429 | 43.0% | -0.07% | 38.1% | -1.6% | 40.2% | -3.09% |
| 📍 Near | 104 | 31.1% | -4.18% | 36.9% | -5.82% | 39.8% | -4.74% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 594 | 43.3% | -1.67% | 38.0% | -3.0% | 38.2% | -4.35% |
| tier2 | 571 | 36.5% | -1.66% | 36.4% | -2.59% | 38.7% | -2.06% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 721 | 37.9% | -3.84% | 39.7% | -4.42% |
| 90-94 | 284 | 38.8% | 0.84% | 38.8% | 0.85% |
| 85-89 | 160 | 31.0% | -4.54% | 31.6% | -5.05% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 143.97 | +128.7% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 143.97 | +127.4% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 143.97 | +126.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 135.61 | +123.9% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 143.97 | +123.3% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 143.97 | +123.3% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| NVTS | 06-17 | 🌀 Coil | 97.5 | 22.34 | 11.46 | -48.7% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |
| BTDR | 06-30 | 🌀 Coil | 87.8 | 15.87 | 8.90 | -43.9% |
| COHR | 06-30 | 📐 Tight | 96.7 | 394.47 | 222.05 | -43.7% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
