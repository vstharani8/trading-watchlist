# Momentum Scan Performance Audit — 2026-10-09

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1646. With forward data: 1646.

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
| EXTENDED | 835 | 40.3% | -1.48% | 42.1% | -2.36% | 39.3% | -1.87% |
| TIGHT | 430 | 42.8% | -0.88% | 45.3% | -0.3% | 52.3% | 3.15% |
| BELOW85 | 216 | 36.6% | -1.71% | 44.0% | -1.26% | 38.0% | -1.62% |
| PULLBACK | 105 | 30.5% | -3.93% | 45.7% | -4.0% | 63.8% | 10.21% |
| EARLY | 60 | 41.7% | -1.48% | 33.3% | -2.87% | 48.3% | -1.79% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 844 | 41.7% | -1.28% | 40.1% | -2.21% | 45.8% | 1.33% |
| <85 | 348 | 36.2% | -1.79% | 44.8% | -1.64% | 38.2% | -2.45% |
| 90-94 | 262 | 38.5% | -2.4% | 48.9% | -1.12% | 53.4% | 2.92% |
| 85-89 | 192 | 40.1% | -0.77% | 45.3% | -1.21% | 37.5% | -3.13% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 142 | 40.1% | -0.55% | 43.7% | -1.14% | 52.1% | 1.1% |
| lifted (0..+5) | 529 | 41.0% | -1.3% | 42.9% | -1.02% | 45.9% | 0.81% |
| extended (>+5) | 835 | 40.3% | -1.48% | 42.1% | -2.36% | 39.3% | -1.87% |
| pullback (-5..-2) | 79 | 31.6% | -3.48% | 46.8% | -1.84% | 57.0% | 8.2% |
| deep-pb (<-5) | 61 | 34.4% | -3.42% | 52.5% | -2.44% | 67.2% | 12.08% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 695 | 40.0% | -1.27% | 45.9% | -0.92% | 46.5% | 0.7% |
| 30-49% | 650 | 40.8% | -1.43% | 41.7% | -2.0% | 40.8% | -1.09% |
| 50+% | 301 | 37.5% | -2.25% | 39.6% | -3.43% | 47.8% | 2.2% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 545 | 61.6% | 8.35% |
| Energy Minerals | 32 | 78.1% | 7.8% |
| Producer Manufacturing | 18 | 44.4% | 1.56% |
| Industrial Services | 28 | 46.4% | 0.45% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Health Services | 33 | 27.3% | -0.28% |
| Technology Services | 396 | 46.0% | -0.87% |
| Consumer Services | 23 | 39.1% | -0.88% |
| Finance | 42 | 42.9% | -1.77% |
| Retail Trade | 15 | 13.3% | -2.97% |
| Electronic Technology | 332 | 28.0% | -6.48% |

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
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 13.31 | +63.5% |

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
