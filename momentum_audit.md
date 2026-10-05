# Momentum Scan Performance Audit — 2026-10-05

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1782. With forward data: 1743.

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
| EXTENDED | 844 | 42.2% | -1.08% | 45.6% | -1.65% | 44.8% | -0.27% |
| TIGHT | 472 | 43.5% | -1.0% | 47.2% | -0.56% | 59.1% | 4.41% |
| BELOW85 | 234 | 38.4% | -1.76% | 42.7% | -1.44% | 40.9% | -1.07% |
| PULLBACK | 125 | 27.2% | -4.76% | 42.4% | -4.72% | 60.0% | 9.11% |
| EARLY | 68 | 40.3% | -1.98% | 32.8% | -3.81% | 50.7% | -2.07% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 882 | 43.4% | -1.05% | 44.5% | -1.53% | 53.5% | 3.26% |
| <85 | 371 | 37.5% | -1.82% | 43.8% | -1.72% | 40.5% | -1.98% |
| 90-94 | 286 | 35.1% | -2.88% | 45.6% | -2.24% | 53.3% | 3.35% |
| 85-89 | 204 | 44.3% | -0.5% | 47.3% | -1.09% | 43.8% | -2.16% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 153 | 41.8% | -0.69% | 45.8% | -1.26% | 56.2% | 2.13% |
| lifted (0..+5) | 582 | 41.0% | -1.52% | 43.5% | -1.37% | 51.2% | 1.8% |
| extended (>+5) | 844 | 42.2% | -1.08% | 45.6% | -1.65% | 44.8% | -0.27% |
| pullback (-5..-2) | 94 | 30.1% | -3.98% | 41.9% | -3.08% | 58.1% | 7.78% |
| deep-pb (<-5) | 70 | 35.7% | -3.7% | 50.0% | -2.56% | 64.3% | 10.12% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 715 | 40.9% | -1.38% | 48.6% | -0.63% | 51.3% | 2.0% |
| 30-49% | 698 | 42.6% | -0.93% | 44.1% | -1.35% | 47.0% | 0.62% |
| 50+% | 330 | 36.7% | -2.76% | 38.3% | -4.52% | 50.9% | 2.28% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 631 | 63.0% | 8.62% |
| Energy Minerals | 32 | 78.1% | 7.4% |
| Transportation | 4 | 75.0% | 5.31% |
| Producer Manufacturing | 21 | 52.4% | 3.4% |
| Industrial Services | 26 | 52.0% | 1.77% |
| Retail Trade | 22 | 31.8% | 1.09% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Technology Services | 394 | 51.0% | 0.26% |
| Finance | 52 | 52.9% | -0.11% |
| Consumer Services | 27 | 40.7% | -0.77% |
| Health Services | 38 | 23.7% | -1.7% |

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
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 14.22 | +74.7% |
| IOVA | 09-09 | TIGHT | 98.6 | +32.4% | 8.43 | 14.22 | +68.7% |
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
