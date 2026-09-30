# Momentum Scan Performance Audit — 2026-09-30

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1902. With forward data: 1884.

Setup proxies are DERIVED (no native label in momentum_scan):
- **TIGHT**: RS≥85 AND dist10 in [-2%, +4%] — same filter as momentum_tight
- **EXTENDED**: dist10 > +5% — already run, late entry
- **PULLBACK**: RS≥85 AND dist10 < -2%
- **EARLY**: RS≥85 AND dist10 in (+4%, +5%]
- **WATCH**: RS≥85 but doesn't fit cleanly
- **BELOW85**: RS<85 (passes momentum criteria but low RS)

## Performance by Setup Proxy

| Setup | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| EXTENDED | 904 | 39.2% | -1.94% | 42.1% | -3.05% | 41.6% | -1.85% |
| TIGHT | 497 | 41.6% | -1.4% | 45.0% | -0.96% | 57.4% | 4.28% |
| BELOW85 | 252 | 34.3% | -2.13% | 39.8% | -1.93% | 41.8% | -0.27% |
| PULLBACK | 141 | 26.4% | -4.8% | 39.3% | -5.49% | 57.9% | 7.46% |
| EARLY | 90 | 28.9% | -4.33% | 25.6% | -6.6% | 46.7% | -3.08% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 958 | 39.3% | -2.05% | 39.9% | -3.05% | 49.0% | 1.61% |
| <85 | 394 | 34.4% | -2.13% | 41.2% | -2.16% | 40.5% | -1.72% |
| 90-94 | 313 | 33.7% | -3.21% | 42.0% | -3.02% | 51.6% | 2.81% |
| 85-89 | 219 | 42.7% | -1.15% | 49.1% | -1.7% | 45.9% | -2.42% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 173 | 41.6% | -0.73% | 43.9% | -1.59% | 53.2% | 1.92% |
| lifted (0..+5) | 627 | 36.3% | -2.34% | 39.7% | -2.27% | 50.5% | 1.85% |
| extended (>+5) | 904 | 39.2% | -1.94% | 42.1% | -3.05% | 41.6% | -1.85% |
| pullback (-5..-2) | 109 | 27.8% | -4.22% | 38.0% | -4.24% | 55.6% | 5.98% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.5% | 63.4% | 9.62% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 762 | 39.0% | -1.7% | 46.6% | -1.45% | 48.7% | 0.91% |
| 30-49% | 761 | 38.2% | -2.05% | 39.5% | -2.59% | 44.9% | -0.01% |
| 50+% | 361 | 33.9% | -3.37% | 35.3% | -5.63% | 49.3% | 1.43% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 7.04% |
| Health Technology | 734 | 61.2% | 6.75% |
| Transportation | 10 | 50.0% | 3.57% |
| Retail Trade | 38 | 39.5% | 3.01% |
| Producer Manufacturing | 31 | 51.6% | 2.39% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Technology Services | 398 | 47.7% | -0.37% |
| Industrial Services | 23 | 31.8% | -0.63% |
| Finance | 64 | 50.8% | -1.78% |
| Consumer Services | 32 | 38.7% | -1.92% |
| Health Services | 48 | 18.8% | -2.33% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 14.45 | +77.5% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.45 | +74.5% |
| IOVA | 09-09 | TIGHT | 98.6 | +32.4% | 8.43 | 14.45 | +71.4% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.45 | +68.0% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| NTLA | 07-03 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-04 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-05 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-06 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| ALOY | 08-15 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
