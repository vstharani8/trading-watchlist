# Momentum Scan Performance Audit — 2026-09-28

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1980. With forward data: 1953.

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
| EXTENDED | 949 | 38.9% | -2.2% | 40.3% | -4.21% | 40.3% | -3.34% |
| TIGHT | 511 | 41.7% | -1.29% | 43.9% | -1.36% | 56.9% | 3.08% |
| BELOW85 | 252 | 34.8% | -2.13% | 40.4% | -1.9% | 42.4% | 0.64% |
| PULLBACK | 144 | 28.0% | -4.49% | 39.2% | -5.63% | 58.0% | 6.53% |
| EARLY | 97 | 29.2% | -4.64% | 26.0% | -7.07% | 46.9% | -3.96% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1003 | 39.2% | -2.29% | 38.0% | -4.3% | 47.4% | -0.68% |
| <85 | 394 | 34.4% | -2.04% | 41.3% | -2.07% | 40.8% | -0.9% |
| 90-94 | 327 | 34.5% | -3.07% | 40.9% | -3.41% | 51.1% | 2.28% |
| 85-89 | 229 | 42.5% | -1.21% | 49.1% | -1.83% | 46.5% | -2.43% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 178 | 40.7% | -0.8% | 42.9% | -1.73% | 53.1% | 1.58% |
| lifted (0..+5) | 643 | 37.0% | -2.29% | 39.3% | -2.62% | 50.5% | 1.17% |
| extended (>+5) | 949 | 38.9% | -2.2% | 40.3% | -4.21% | 40.3% | -3.34% |
| pullback (-5..-2) | 112 | 29.7% | -3.83% | 37.8% | -4.45% | 55.9% | 5.34% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.5% | 63.4% | 9.27% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 789 | 39.5% | -1.6% | 45.4% | -1.91% | 48.5% | 0.32% |
| 30-49% | 786 | 37.5% | -2.3% | 38.5% | -3.59% | 44.0% | -1.06% |
| 50+% | 378 | 35.1% | -3.46% | 34.3% | -6.11% | 47.9% | -0.68% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 7.02% |
| Health Technology | 774 | 60.3% | 4.64% |
| Retail Trade | 43 | 44.2% | 3.7% |
| Transportation | 12 | 41.7% | 1.26% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 21 | 40.0% | -0.06% |
| Technology Services | 401 | 44.8% | -1.05% |
| Finance | 66 | 52.3% | -1.6% |
| Consumer Services | 33 | 36.4% | -2.42% |
| Health Services | 52 | 19.2% | -2.51% |
| Producer Manufacturing | 40 | 40.0% | -2.91% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |
| PSNL | 07-24 | PULLBACK | 94.3 | +23.7% | 11.78 | 18.38 | +56.0% |
| IOVA | 07-22 | EXTENDED | 96.1 | +38.0% | 5.17 | 7.99 | +54.5% |
| ABCL | 07-15 | PULLBACK | 92.6 | +27.2% | 6.74 | 10.35 | +53.6% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| OUST | 07-01 | EXTENDED | 97.7 | +40.0% | 60.02 | 35.53 | -40.8% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| MXL | 07-01 | EXTENDED | 99.8 | +29.0% | 112.39 | 66.92 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| NTLA | 07-03 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-04 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-05 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
