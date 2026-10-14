# Momentum Scan Performance Audit — 2026-10-14

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1485. With forward data: 1485.

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
| EXTENDED | 799 | 41.6% | -1.28% | 43.4% | -2.18% | 37.5% | -2.42% |
| TIGHT | 363 | 46.6% | -0.28% | 47.1% | 0.3% | 49.3% | 3.16% |
| BELOW85 | 191 | 40.3% | -1.16% | 47.6% | -0.15% | 38.7% | -1.07% |
| PULLBACK | 76 | 36.8% | -2.41% | 53.9% | -1.2% | 67.1% | 10.25% |
| EARLY | 56 | 41.1% | -1.47% | 35.7% | -2.64% | 46.4% | -1.64% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 775 | 43.6% | -0.85% | 41.5% | -1.74% | 43.0% | 1.08% |
| <85 | 319 | 38.9% | -1.44% | 47.0% | -1.03% | 37.9% | -2.47% |
| 90-94 | 223 | 43.6% | -1.69% | 52.7% | 0.02% | 51.8% | 1.74% |
| 85-89 | 168 | 42.3% | -0.65% | 48.2% | -1.3% | 36.3% | -4.08% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 116 | 44.0% | 0.04% | 47.4% | -0.02% | 50.0% | 1.32% |
| lifted (0..+5) | 460 | 44.3% | -0.75% | 44.8% | -0.45% | 43.9% | 0.81% |
| extended (>+5) | 799 | 41.6% | -1.28% | 43.4% | -2.18% | 37.5% | -2.42% |
| pullback (-5..-2) | 63 | 39.7% | -1.63% | 54.0% | 1.21% | 60.3% | 8.42% |
| deep-pb (<-5) | 47 | 36.2% | -3.09% | 59.6% | -0.57% | 68.1% | 12.15% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 639 | 41.8% | -0.85% | 47.9% | -0.47% | 45.1% | 0.32% |
| 30-49% | 578 | 43.3% | -1.15% | 42.2% | -1.82% | 36.5% | -2.1% |
| 50+% | 268 | 42.1% | -1.51% | 44.8% | -2.04% | 49.6% | 2.94% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 451 | 62.3% | 9.93% |
| Energy Minerals | 32 | 78.1% | 8.06% |
| Industrial Services | 28 | 53.6% | 2.83% |
| Producer Manufacturing | 16 | 50.0% | 1.7% |
| Health Services | 28 | 32.1% | 0.92% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Technology Services | 370 | 47.3% | -0.82% |
| Consumer Services | 21 | 33.3% | -1.16% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Electronic Technology | 315 | 21.9% | -8.31% |
| Finance | 29 | 24.1% | -8.41% |

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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 16.48 | -57.4% |
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
