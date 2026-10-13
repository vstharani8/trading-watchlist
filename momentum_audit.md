# Momentum Scan Performance Audit — 2026-10-13

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1507. With forward data: 1507.

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
| EXTENDED | 807 | 41.7% | -1.27% | 43.7% | -2.04% | 38.3% | -2.13% |
| TIGHT | 369 | 46.2% | -0.35% | 47.6% | 0.19% | 50.5% | 3.13% |
| BELOW85 | 193 | 39.9% | -1.2% | 47.2% | -0.28% | 38.3% | -1.26% |
| PULLBACK | 81 | 34.6% | -2.76% | 53.1% | -1.16% | 69.1% | 11.48% |
| EARLY | 57 | 40.4% | -1.59% | 35.1% | -2.73% | 47.4% | -1.66% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 783 | 43.6% | -0.83% | 42.2% | -1.59% | 44.3% | 1.36% |
| <85 | 322 | 38.5% | -1.49% | 46.6% | -1.13% | 37.9% | -2.51% |
| 90-94 | 231 | 42.7% | -1.88% | 52.0% | -0.09% | 53.3% | 2.21% |
| 85-89 | 171 | 41.5% | -0.77% | 48.0% | -1.39% | 36.3% | -4.0% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 118 | 44.1% | 0.07% | 46.6% | -0.23% | 50.8% | 1.31% |
| lifted (0..+5) | 467 | 43.8% | -0.84% | 45.1% | -0.54% | 44.6% | 0.73% |
| extended (>+5) | 807 | 41.7% | -1.27% | 43.7% | -2.04% | 38.3% | -2.13% |
| pullback (-5..-2) | 66 | 37.9% | -2.06% | 53.0% | 0.93% | 62.1% | 9.66% |
| deep-pb (<-5) | 49 | 34.7% | -3.12% | 59.2% | -0.35% | 69.4% | 12.49% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 648 | 41.4% | -0.88% | 48.0% | -0.43% | 46.1% | 0.64% |
| 30-49% | 586 | 42.7% | -1.25% | 41.9% | -1.85% | 36.9% | -1.97% |
| 50+% | 273 | 42.8% | -1.46% | 46.3% | -1.9% | 51.0% | 3.11% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 466 | 64.1% | 10.23% |
| Energy Minerals | 32 | 78.1% | 7.86% |
| Industrial Services | 28 | 53.6% | 3.55% |
| Producer Manufacturing | 16 | 50.0% | 1.78% |
| Health Services | 29 | 31.0% | 0.63% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Technology Services | 374 | 47.6% | -0.65% |
| Consumer Services | 21 | 33.3% | -1.26% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Finance | 31 | 29.0% | -6.58% |
| Electronic Technology | 315 | 21.9% | -8.48% |

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
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.62 | +70.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 16.91 | -56.2% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| ALOY | 08-15 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| ALOY | 08-17 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| AAOI | 08-15 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |
| AAOI | 08-17 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
