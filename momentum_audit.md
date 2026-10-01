# Momentum Scan Performance Audit — 2026-10-01

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1886. With forward data: 1861.

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
| EXTENDED | 897 | 39.4% | -1.84% | 42.4% | -2.88% | 42.1% | -1.66% |
| TIGHT | 492 | 41.2% | -1.41% | 44.7% | -1.02% | 57.2% | 4.18% |
| BELOW85 | 249 | 35.5% | -2.06% | 40.7% | -1.87% | 41.9% | -0.53% |
| PULLBACK | 138 | 26.8% | -4.76% | 39.9% | -5.28% | 58.7% | 7.76% |
| EARLY | 85 | 30.6% | -3.91% | 25.9% | -6.18% | 48.2% | -2.87% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 947 | 39.8% | -1.92% | 40.4% | -2.87% | 49.8% | 1.77% |
| <85 | 390 | 35.0% | -2.1% | 41.6% | -2.15% | 40.4% | -1.89% |
| 90-94 | 308 | 33.4% | -3.18% | 42.2% | -2.92% | 52.3% | 2.96% |
| 85-89 | 216 | 42.3% | -1.05% | 47.4% | -1.63% | 44.7% | -2.43% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 169 | 40.8% | -0.78% | 43.2% | -1.62% | 52.7% | 1.69% |
| lifted (0..+5) | 618 | 37.0% | -2.23% | 40.1% | -2.19% | 50.6% | 1.76% |
| extended (>+5) | 897 | 39.4% | -1.84% | 42.4% | -2.88% | 42.1% | -1.66% |
| pullback (-5..-2) | 106 | 28.3% | -4.16% | 38.7% | -3.95% | 56.6% | 6.28% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.5% | 64.8% | 9.99% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 754 | 38.6% | -1.73% | 45.9% | -1.46% | 48.6% | 0.96% |
| 30-49% | 751 | 38.8% | -1.88% | 40.0% | -2.41% | 45.3% | 0.03% |
| 50+% | 356 | 34.9% | -3.21% | 36.6% | -5.4% | 50.6% | 1.6% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 78.1% | 7.16% |
| Health Technology | 716 | 61.3% | 7.12% |
| Transportation | 9 | 55.6% | 4.14% |
| Retail Trade | 35 | 40.0% | 3.02% |
| Producer Manufacturing | 29 | 51.7% | 2.48% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 24 | 47.8% | 0.3% |
| Technology Services | 397 | 48.7% | -0.39% |
| Consumer Services | 31 | 38.7% | -1.54% |
| Finance | 62 | 49.2% | -1.75% |
| Health Services | 46 | 19.6% | -2.18% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 14.82 | +82.1% |
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 09-09 | TIGHT | 98.6 | +32.4% | 8.43 | 14.82 | +75.8% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.82 | +72.3% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| NTLA | 07-04 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-05 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| NTLA | 07-06 | EXTENDED | 89.6 | +30.3% | 17.84 | 10.77 | -39.6% |
| ALOY | 08-15 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| ALOY | 08-17 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
