# Pattern Performance Audit — 2026-08-12

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 978. With forward data: 978.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 551 | 43.9% | -1.73% | 41.9% | -2.46% | 40.6% | -4.49% |
| 🌀 Coil | 351 | 46.0% | -1.1% | 42.8% | -1.95% | 38.6% | -5.96% |
| 📍 Near | 76 | 30.3% | -4.35% | 44.7% | -4.84% | 39.5% | -6.41% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 498 | 45.0% | -1.65% | 42.3% | -2.28% | 38.8% | -5.36% |
| tier2 | 480 | 42.1% | -1.77% | 42.6% | -2.67% | 40.9% | -4.96% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 616 | 42.4% | -2.69% | 38.4% | -5.85% |
| 90-94 | 241 | 46.0% | -1.23% | 45.1% | -2.84% |
| 85-89 | 121 | 35.8% | -3.8% | 36.7% | -6.27% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| DFTX | 06-09 | 📐 Tight | 94.3 | 22.95 | 48.45 | +111.1% |
| DFTX | 06-08 | 📐 Tight | 95.1 | 23.02 | 45.32 | +96.9% |
| DFTX | 06-11 | 📐 Tight | 94.9 | 24.11 | 43.65 | +81.0% |
| DFTX | 06-04 | 📐 Tight | 93.9 | 24.59 | 44.33 | +80.3% |
| RLAY | 06-10 | 📐 Tight | 97.1 | 13.49 | 20.00 | +48.3% |
| RLAY | 06-09 | 📐 Tight | 96.7 | 14.09 | 20.75 | +47.3% |
| FSLY | 07-23 | 📐 Tight | 95.6 | 19.43 | 28.53 | +46.8% |
| RLAY | 06-05 | 📐 Tight | 96.6 | 13.52 | 19.74 | +46.0% |
| RLAY | 06-08 | 📐 Tight | 96.8 | 13.66 | 19.63 | +43.7% |
| FSLY | 07-27 | 📐 Tight | 95.9 | 20.04 | 28.53 | +42.4% |

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
