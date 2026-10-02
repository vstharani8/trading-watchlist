# Momentum Scan Performance Audit — 2026-10-02

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1872. With forward data: 1845.

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
| EXTENDED | 889 | 39.9% | -1.73% | 42.7% | -2.74% | 42.8% | -1.53% |
| TIGHT | 492 | 41.8% | -1.3% | 45.3% | -0.92% | 58.4% | 4.06% |
| BELOW85 | 246 | 36.3% | -2.02% | 41.2% | -1.83% | 42.0% | -0.85% |
| PULLBACK | 135 | 27.4% | -4.71% | 40.7% | -5.09% | 57.8% | 7.86% |
| EARLY | 83 | 33.8% | -3.4% | 27.5% | -5.53% | 48.8% | -2.57% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 941 | 40.6% | -1.74% | 41.2% | -2.62% | 50.5% | 1.86% |
| <85 | 386 | 36.1% | -2.05% | 42.3% | -2.15% | 40.8% | -2.14% |
| 90-94 | 303 | 34.0% | -3.13% | 43.2% | -2.75% | 53.8% | 3.14% |
| 85-89 | 215 | 42.5% | -0.99% | 46.2% | -1.66% | 43.9% | -2.57% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 166 | 40.6% | -0.8% | 43.0% | -1.61% | 53.3% | 1.55% |
| lifted (0..+5) | 616 | 38.4% | -2.03% | 41.2% | -1.99% | 51.5% | 1.63% |
| extended (>+5) | 889 | 39.9% | -1.73% | 42.7% | -2.74% | 42.8% | -1.53% |
| pullback (-5..-2) | 103 | 29.1% | -4.08% | 39.8% | -3.65% | 57.3% | 6.56% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.5% | 62.0% | 9.77% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 749 | 39.5% | -1.66% | 47.0% | -1.31% | 49.9% | 1.11% |
| 30-49% | 745 | 39.8% | -1.69% | 40.7% | -2.26% | 45.9% | -0.02% |
| 50+% | 351 | 34.8% | -3.14% | 36.0% | -5.26% | 49.6% | 1.39% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 78.1% | 7.54% |
| Health Technology | 700 | 61.1% | 6.99% |
| Transportation | 8 | 62.5% | 4.85% |
| Retail Trade | 32 | 40.6% | 3.05% |
| Producer Manufacturing | 27 | 51.9% | 2.93% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 25 | 50.0% | 0.36% |
| Technology Services | 397 | 49.9% | -0.26% |
| Consumer Services | 30 | 40.0% | -1.31% |
| Finance | 60 | 50.8% | -1.54% |
| Health Services | 44 | 20.5% | -2.18% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 14.23 | +74.8% |
| IOVA | 09-09 | TIGHT | 98.6 | +32.4% | 8.43 | 14.23 | +68.8% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| NTLA | 07-05 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-06 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| ALOY | 08-15 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| ALOY | 08-17 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| AAOI | 08-15 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
