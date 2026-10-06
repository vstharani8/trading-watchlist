# Momentum Scan Performance Audit — 2026-10-06

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1780. With forward data: 1742.

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
| EXTENDED | 849 | 43.3% | -0.82% | 48.3% | -1.06% | 47.7% | 0.55% |
| TIGHT | 472 | 44.3% | -0.95% | 48.0% | -0.44% | 59.1% | 4.49% |
| BELOW85 | 234 | 37.5% | -1.81% | 42.2% | -1.5% | 40.1% | -0.96% |
| PULLBACK | 119 | 26.9% | -4.73% | 42.9% | -4.68% | 60.5% | 9.83% |
| EARLY | 68 | 41.8% | -1.41% | 32.8% | -3.08% | 53.7% | -1.01% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 886 | 44.8% | -0.76% | 46.2% | -1.04% | 54.8% | 3.93% |
| <85 | 369 | 36.6% | -1.88% | 44.3% | -1.65% | 41.0% | -1.52% |
| 90-94 | 285 | 36.3% | -2.74% | 48.4% | -1.92% | 56.9% | 3.6% |
| 85-89 | 202 | 44.2% | -0.4% | 48.2% | -0.75% | 43.7% | -1.97% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 150 | 41.6% | -0.65% | 45.0% | -1.26% | 55.0% | 2.11% |
| lifted (0..+5) | 584 | 41.7% | -1.43% | 44.3% | -1.21% | 51.8% | 2.06% |
| extended (>+5) | 849 | 43.3% | -0.82% | 48.3% | -1.06% | 47.7% | 0.55% |
| pullback (-5..-2) | 89 | 29.5% | -3.86% | 42.0% | -2.89% | 56.8% | 8.47% |
| deep-pb (<-5) | 70 | 35.7% | -3.7% | 50.0% | -2.56% | 64.3% | 10.12% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 718 | 41.7% | -1.2% | 50.0% | -0.29% | 53.0% | 2.46% |
| 30-49% | 694 | 43.2% | -0.83% | 45.5% | -1.11% | 48.0% | 0.98% |
| 50+% | 330 | 37.7% | -2.48% | 40.3% | -3.89% | 52.4% | 3.19% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 615 | 65.4% | 10.0% |
| Energy Minerals | 32 | 78.1% | 7.59% |
| Transportation | 3 | 66.7% | 3.39% |
| Producer Manufacturing | 21 | 50.0% | 2.48% |
| Industrial Services | 27 | 50.0% | 1.63% |
| Finance | 50 | 60.4% | 0.97% |
| Technology Services | 400 | 53.2% | 0.86% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Retail Trade | 20 | 25.0% | -0.16% |
| Consumer Services | 26 | 42.3% | -0.72% |
| Health Services | 37 | 27.0% | -1.52% |

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
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 14.15 | +73.8% |
| IOVA | 09-09 | TIGHT | 98.6 | +32.4% | 8.43 | 14.15 | +67.8% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| ALOY | 08-15 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| ALOY | 08-17 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| AAOI | 08-15 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |
| AAOI | 08-17 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |
| AEHR | 08-14 | EXTENDED | 99.6 | +68.2% | 134.06 | 83.37 | -37.8% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
