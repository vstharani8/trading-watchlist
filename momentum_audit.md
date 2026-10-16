# Momentum Scan Performance Audit — 2026-10-16

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1443. With forward data: 1443.

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
| EXTENDED | 789 | 41.7% | -1.25% | 42.8% | -2.84% | 35.2% | -3.89% |
| TIGHT | 342 | 48.0% | -0.06% | 46.8% | -0.24% | 47.1% | 1.82% |
| BELOW85 | 186 | 41.4% | -1.04% | 46.8% | -0.38% | 36.6% | -1.85% |
| PULLBACK | 72 | 38.9% | -2.03% | 54.2% | -0.88% | 65.3% | 8.8% |
| EARLY | 54 | 42.6% | -1.31% | 35.2% | -2.96% | 40.7% | -3.33% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 757 | 44.0% | -0.79% | 41.0% | -2.56% | 40.2% | -0.82% |
| <85 | 312 | 39.7% | -1.32% | 46.8% | -1.22% | 35.6% | -3.45% |
| 90-94 | 213 | 44.3% | -1.53% | 52.4% | -0.18% | 50.5% | 0.74% |
| 85-89 | 161 | 43.5% | -0.45% | 46.6% | -1.53% | 33.5% | -4.61% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 110 | 45.5% | 0.18% | 48.2% | 0.11% | 48.2% | 0.96% |
| lifted (0..+5) | 439 | 45.6% | -0.56% | 43.7% | -1.11% | 40.8% | -0.79% |
| extended (>+5) | 789 | 41.7% | -1.25% | 42.8% | -2.84% | 35.2% | -3.89% |
| pullback (-5..-2) | 61 | 41.0% | -1.43% | 54.1% | 1.58% | 59.0% | 7.13% |
| deep-pb (<-5) | 44 | 38.6% | -2.68% | 61.4% | 0.03% | 68.2% | 12.23% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 618 | 42.6% | -0.75% | 47.1% | -0.97% | 41.9% | -1.54% |
| 30-49% | 566 | 43.5% | -1.12% | 41.5% | -2.51% | 34.3% | -3.5% |
| 50+% | 259 | 43.3% | -1.23% | 45.3% | -2.27% | 48.2% | 2.68% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 425 | 61.8% | 10.18% |
| Energy Minerals | 32 | 78.1% | 7.84% |
| Health Services | 26 | 30.8% | 1.16% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | 0.36% |
| Consumer Services | 21 | 33.3% | -1.22% |
| Technology Services | 359 | 46.2% | -2.02% |
| Industrial Services | 27 | 22.2% | -3.5% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Non-Energy Minerals | 147 | 16.3% | -11.0% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.62 | +70.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 13.31 | +63.5% |
| IOVA | 09-03 | EXTENDED | 98.8 | +110.2% | 8.70 | 14.22 | +63.5% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 16.07 | -58.4% |
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
