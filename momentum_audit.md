# Momentum Scan Performance Audit — 2026-10-08

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1689. With forward data: 1689.

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
| EXTENDED | 842 | 40.6% | -1.29% | 43.5% | -1.88% | 41.4% | -1.08% |
| TIGHT | 452 | 44.2% | -0.72% | 47.1% | -0.07% | 55.5% | 3.62% |
| BELOW85 | 223 | 35.9% | -1.72% | 43.5% | -1.15% | 38.1% | -1.26% |
| PULLBACK | 111 | 29.7% | -4.12% | 45.9% | -4.21% | 64.9% | 10.09% |
| EARLY | 61 | 44.3% | -1.03% | 34.4% | -2.46% | 54.1% | -1.12% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 864 | 42.5% | -1.09% | 41.9% | -1.73% | 49.1% | 2.13% |
| <85 | 355 | 35.8% | -1.78% | 44.8% | -1.43% | 38.9% | -1.96% |
| 90-94 | 270 | 37.4% | -2.38% | 48.5% | -1.17% | 54.1% | 3.35% |
| 85-89 | 200 | 43.5% | -0.52% | 48.0% | -0.87% | 41.0% | -2.62% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 149 | 40.9% | -0.67% | 45.6% | -1.2% | 54.4% | 1.29% |
| lifted (0..+5) | 552 | 42.0% | -1.1% | 43.8% | -0.71% | 48.7% | 1.41% |
| extended (>+5) | 842 | 40.6% | -1.29% | 43.5% | -1.88% | 41.4% | -1.08% |
| pullback (-5..-2) | 82 | 30.5% | -3.62% | 47.6% | -2.0% | 58.5% | 8.06% |
| deep-pb (<-5) | 64 | 34.4% | -3.55% | 51.6% | -2.7% | 67.2% | 12.13% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 710 | 41.3% | -1.12% | 48.2% | -0.5% | 50.4% | 1.47% |
| 30-49% | 669 | 41.3% | -1.2% | 42.9% | -1.51% | 42.5% | -0.33% |
| 50+% | 310 | 36.4% | -2.35% | 38.4% | -3.68% | 47.7% | 2.27% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 569 | 61.1% | 8.24% |
| Energy Minerals | 32 | 78.1% | 7.65% |
| Industrial Services | 28 | 53.6% | 2.14% |
| Producer Manufacturing | 19 | 47.4% | 1.81% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Health Services | 34 | 26.5% | -0.34% |
| Technology Services | 401 | 46.4% | -0.47% |
| Consumer Services | 24 | 41.7% | -0.65% |
| Finance | 45 | 44.4% | -0.87% |
| Retail Trade | 16 | 18.8% | -1.57% |
| Electronic Technology | 339 | 37.8% | -4.37% |

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
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |
| IOVA | 09-03 | EXTENDED | 98.8 | +110.2% | 8.70 | 14.22 | +63.5% |

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
