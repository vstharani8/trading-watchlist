# Pattern Performance Audit — 2026-08-11

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 982. With forward data: 962.

> Each scan appearance is treated as an independent entry signal. Tickers appearing
> on consecutive days are NOT deduped — pattern repeat-ability is part of the answer.

## Performance by Setup Type

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 📐 Tight | 540 | 39.7% | -2.37% | 36.1% | -3.35% | 33.3% | -6.1% |
| 🌀 Coil | 343 | 42.7% | -1.55% | 39.3% | -2.44% | 33.1% | -7.36% |
| 📍 Near | 79 | 26.0% | -4.57% | 40.3% | -4.92% | 33.8% | -7.16% |

## Performance by Tier

| Tier | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tier1 | 488 | 41.4% | -2.1% | 37.6% | -2.89% | 32.2% | -6.92% |
| tier2 | 474 | 37.8% | -2.44% | 37.6% | -3.43% | 34.5% | -6.36% |

## Performance by RS Bucket

| RS Bucket | N | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|
| 95+ | 605 | 36.5% | -3.49% | 30.7% | -7.58% |
| 90-94 | 232 | 42.6% | -1.85% | 40.7% | -3.97% |
| 85-89 | 125 | 33.9% | -3.92% | 32.2% | -7.04% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|
| DFTX | 06-09 | 📐 Tight | 94.3 | 22.95 | 48.45 | +111.1% |
| DFTX | 06-08 | 📐 Tight | 95.1 | 23.02 | 45.32 | +96.9% |
| DFTX | 06-11 | 📐 Tight | 94.9 | 24.11 | 43.65 | +81.0% |
| DFTX | 06-04 | 📐 Tight | 93.9 | 24.59 | 44.33 | +80.3% |
| RLAY | 06-10 | 📐 Tight | 97.1 | 13.49 | 20.00 | +48.3% |
| RLAY | 06-09 | 📐 Tight | 96.7 | 14.09 | 20.75 | +47.3% |
| RLAY | 06-05 | 📐 Tight | 96.6 | 13.52 | 19.74 | +46.0% |
| RLAY | 06-08 | 📐 Tight | 96.8 | 13.66 | 19.63 | +43.7% |
| FSLY | 07-23 | 📐 Tight | 95.6 | 19.43 | 27.75 | +42.8% |
| ERAS | 06-04 | 📐 Tight | 99.4 | 13.27 | 18.85 | +42.0% |

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
