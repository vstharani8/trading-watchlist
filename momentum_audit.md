# Momentum Scan Performance Audit — 2026-10-15

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1466. With forward data: 1466.

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
| EXTENDED | 795 | 41.7% | -1.25% | 42.8% | -2.75% | 35.6% | -3.74% |
| TIGHT | 353 | 47.6% | -0.13% | 46.7% | -0.23% | 47.6% | 2.1% |
| BELOW85 | 189 | 40.7% | -1.09% | 47.1% | -0.4% | 37.6% | -1.67% |
| PULLBACK | 73 | 38.4% | -2.13% | 54.8% | -0.86% | 65.8% | 9.96% |
| EARLY | 56 | 41.1% | -1.47% | 33.9% | -3.02% | 41.1% | -2.95% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 767 | 43.8% | -0.81% | 40.8% | -2.45% | 40.5% | -0.48% |
| <85 | 316 | 39.2% | -1.38% | 46.8% | -1.27% | 36.7% | -3.39% |
| 90-94 | 219 | 44.0% | -1.6% | 52.3% | -0.17% | 50.9% | 1.17% |
| 85-89 | 164 | 43.3% | -0.46% | 47.6% | -1.51% | 34.1% | -4.59% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 113 | 44.2% | 0.12% | 47.8% | -0.02% | 48.7% | 1.05% |
| lifted (0..+5) | 452 | 45.1% | -0.64% | 43.8% | -1.06% | 41.6% | -0.43% |
| extended (>+5) | 795 | 41.7% | -1.25% | 42.8% | -2.75% | 35.6% | -3.74% |
| pullback (-5..-2) | 62 | 40.3% | -1.56% | 54.8% | 1.47% | 59.7% | 8.42% |
| deep-pb (<-5) | 44 | 38.6% | -2.68% | 61.4% | 0.03% | 68.2% | 12.23% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 630 | 42.2% | -0.77% | 47.5% | -0.93% | 42.7% | -1.16% |
| 30-49% | 572 | 43.5% | -1.11% | 41.8% | -2.35% | 34.8% | -3.17% |
| 50+% | 264 | 42.6% | -1.36% | 43.8% | -2.43% | 48.2% | 2.44% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 439 | 61.8% | 9.99% |
| Energy Minerals | 32 | 78.1% | 7.92% |
| Health Services | 27 | 33.3% | 1.21% |
| Producer Manufacturing | 16 | 50.0% | 0.67% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 28 | 32.1% | -1.4% |
| Consumer Services | 21 | 33.3% | -1.43% |
| Technology Services | 365 | 46.3% | -2.13% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Electronic Technology | 315 | 17.5% | -11.0% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.62 | +70.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 13.31 | +63.5% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 15.26 | -60.5% |
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
