# Momentum Scan Performance Audit — 2026-10-07

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1736. With forward data: 1736.

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
| EXTENDED | 863 | 42.2% | -1.16% | 45.5% | -1.68% | 44.3% | -0.53% |
| TIGHT | 467 | 44.4% | -0.71% | 47.3% | -0.15% | 57.3% | 4.0% |
| BELOW85 | 230 | 37.3% | -1.69% | 43.4% | -1.18% | 39.9% | -0.93% |
| PULLBACK | 112 | 29.5% | -4.19% | 46.4% | -4.16% | 64.3% | 10.1% |
| EARLY | 64 | 42.2% | -1.11% | 32.8% | -2.82% | 53.1% | -0.84% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 886 | 43.5% | -0.99% | 43.2% | -1.56% | 51.2% | 2.66% |
| <85 | 365 | 36.7% | -1.78% | 45.0% | -1.44% | 40.6% | -1.63% |
| 90-94 | 279 | 38.5% | -2.4% | 50.2% | -1.37% | 57.5% | 3.72% |
| 85-89 | 206 | 44.0% | -0.32% | 48.0% | -0.71% | 42.0% | -2.18% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 151 | 40.9% | -0.63% | 44.3% | -1.23% | 54.4% | 1.79% |
| lifted (0..+5) | 573 | 42.3% | -1.11% | 44.2% | -0.82% | 50.6% | 1.77% |
| extended (>+5) | 863 | 42.2% | -1.16% | 45.5% | -1.68% | 44.3% | -0.53% |
| pullback (-5..-2) | 82 | 30.5% | -3.61% | 47.6% | -1.98% | 59.8% | 8.2% |
| deep-pb (<-5) | 67 | 35.8% | -3.49% | 50.7% | -2.62% | 65.7% | 11.38% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 723 | 41.8% | -1.07% | 49.3% | -0.3% | 52.1% | 2.08% |
| 30-49% | 686 | 42.6% | -0.97% | 44.1% | -1.29% | 45.3% | 0.16% |
| 50+% | 327 | 37.4% | -2.6% | 38.7% | -4.16% | 49.4% | 2.24% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 596 | 61.4% | 8.42% |
| Energy Minerals | 32 | 78.1% | 7.64% |
| Transportation | 2 | 100.0% | 5.86% |
| Industrial Services | 28 | 55.6% | 3.9% |
| Producer Manufacturing | 21 | 50.0% | 1.8% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Technology Services | 405 | 49.6% | 0.19% |
| Consumer Services | 25 | 44.0% | -0.4% |
| Finance | 48 | 50.0% | -0.49% |
| Health Services | 36 | 28.6% | -0.93% |
| Retail Trade | 19 | 21.1% | -0.97% |

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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 19.20 | -50.3% |
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
