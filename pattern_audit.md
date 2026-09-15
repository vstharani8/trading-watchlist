# Pattern Performance Audit — 2026-09-15

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1181. With forward data: 1165.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 635 | 38.5% | -2.54% | 36.4% | -3.32% | 36.1% | -3.49% |
| 🌀 Coil | 425 | 41.9% | -0.27% | 36.2% | -1.73% | 36.9% | -3.36% |
| 📍 Near | 105 | 32.7% | -4.14% | 37.5% | -5.95% | 38.5% | -5.16% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 594 | 43.5% | -1.69% | 37.8% | -2.91% | 36.5% | -4.33% |
| tier2 | 571 | 34.8% | -2.03% | 34.9% | -3.04% | 36.7% | -2.82% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 718 | 35.5% | -4.25% | 34.9% | -5.21% |
| 90-94 | 282 | 40.9% | 1.04% | 41.3% | 0.8% |
| 85-89 | 165 | 32.5% | -4.41% | 35.6% | -4.17% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| MRNA | 08-08 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-09 | 📐 Tight | 90.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-10 | 📐 Tight | 91.7 | 59.81 | 140.33 | +134.6% |
| MRNA | 08-18 | 📐 Tight | 92.1 | 62.96 | 146.69 | +133.0% |
| MRNA | 08-14 | 🌀 Coil | 93.1 | 63.32 | 146.69 | +131.7% |
| MRNA | 08-15 | 🌀 Coil | 92.3 | 64.46 | 146.69 | +127.6% |
| MRNA | 08-17 | 🌀 Coil | 92.3 | 64.46 | 146.69 | +127.6% |
| MRNA | 08-13 | 🌀 Coil | 92.7 | 63.65 | 143.97 | +126.2% |
| MRNA | 08-11 | 📐 Tight | 91.4 | 60.57 | 135.61 | +123.9% |
| AMLX | 07-22 | 📐 Tight | 85.5 | 17.70 | 38.60 | +118.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| NVTS | 06-18 | 🌀 Coil | 98.1 | 24.02 | 11.54 | -52.0% |
| WOLF | 06-26 | 📐 Tight | 100.0 | 45.97 | 23.80 | -48.2% |
| FORM | 06-30 | 📐 Tight | 96.5 | 159.93 | 83.45 | -47.8% |
| WOLF | 07-01 | 📐 Tight | 100.0 | 44.56 | 23.79 | -46.6% |
| NBIS | 06-30 | 📍 Near | 98.5 | 276.17 | 148.22 | -46.3% |
| BE | 06-30 | 📐 Tight | 99.7 | 302.70 | 163.75 | -45.9% |
| NVTS | 06-19 | 🌀 Coil | 98.1 | 23.70 | 12.82 | -45.9% |
| BTDR | 06-30 | 🌀 Coil | 87.8 | 15.87 | 8.90 | -43.9% |
| COHR | 06-30 | 📐 Tight | 96.7 | 394.47 | 222.05 | -43.7% |
| GFS | 06-30 | 📐 Tight | 94.3 | 82.41 | 47.07 | -42.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup type to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: tier preference]
