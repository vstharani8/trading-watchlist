# Momentum Scan Performance Audit — 2026-09-29

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1939. With forward data: 1922.

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
| EXTENDED | 921 | 37.7% | -2.3% | 40.4% | -3.78% | 39.3% | -2.92% |
| TIGHT | 511 | 40.6% | -1.41% | 43.0% | -1.36% | 55.2% | 2.98% |
| BELOW85 | 251 | 34.3% | -2.13% | 39.8% | -1.93% | 41.8% | -0.17% |
| PULLBACK | 144 | 27.8% | -4.48% | 38.9% | -5.61% | 57.6% | 6.45% |
| EARLY | 95 | 27.4% | -4.85% | 24.2% | -7.06% | 45.3% | -3.93% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 982 | 37.6% | -2.35% | 37.2% | -3.92% | 46.0% | -0.15% |
| <85 | 395 | 33.6% | -2.15% | 40.5% | -2.21% | 39.9% | -1.6% |
| 90-94 | 321 | 34.1% | -3.23% | 42.3% | -3.25% | 51.4% | 2.35% |
| 85-89 | 224 | 42.2% | -1.28% | 48.9% | -1.78% | 45.3% | -2.62% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 176 | 40.3% | -0.8% | 42.6% | -1.77% | 51.7% | 1.36% |
| lifted (0..+5) | 642 | 35.7% | -2.41% | 38.2% | -2.62% | 49.0% | 0.86% |
| extended (>+5) | 921 | 37.7% | -2.3% | 40.4% | -3.78% | 39.3% | -2.92% |
| pullback (-5..-2) | 112 | 29.5% | -3.83% | 37.5% | -4.44% | 55.4% | 4.96% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.5% | 63.4% | 9.4% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 779 | 38.2% | -1.81% | 45.2% | -1.82% | 47.2% | 0.23% |
| 30-49% | 774 | 36.7% | -2.29% | 37.7% | -3.26% | 42.9% | -0.98% |
| 50+% | 369 | 33.7% | -3.54% | 34.3% | -6.0% | 47.9% | -0.11% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 6.95% |
| Health Technology | 754 | 59.8% | 5.06% |
| Retail Trade | 41 | 43.9% | 3.45% |
| Transportation | 11 | 45.5% | 2.25% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 22 | 33.3% | -0.43% |
| Producer Manufacturing | 36 | 44.4% | -0.46% |
| Technology Services | 402 | 46.6% | -0.82% |
| Finance | 64 | 50.0% | -1.97% |
| Consumer Services | 32 | 37.5% | -2.3% |
| Health Services | 50 | 18.0% | -2.47% |

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
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| NTLA | 07-03 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-04 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-05 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-06 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-02 | EXTENDED | 88.5 | +25.3% | 17.56 | 10.68 | -39.2% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
