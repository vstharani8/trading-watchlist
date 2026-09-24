# Momentum Scan Performance Audit — 2026-09-24

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2122. With forward data: 2100.

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
| EXTENDED | 1066 | 36.7% | -2.83% | 36.8% | -5.02% | 37.0% | -5.28% |
| TIGHT | 524 | 40.2% | -1.83% | 41.7% | -2.15% | 55.4% | 1.51% |
| BELOW85 | 252 | 35.5% | -2.0% | 41.0% | -1.67% | 46.2% | 0.84% |
| PULLBACK | 149 | 28.9% | -4.66% | 39.6% | -5.76% | 55.7% | 5.04% |
| EARLY | 109 | 27.1% | -5.53% | 24.3% | -7.75% | 43.0% | -7.3% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1089 | 35.3% | -3.4% | 34.1% | -5.46% | 42.2% | -3.54% |
| <85 | 395 | 35.5% | -2.02% | 42.4% | -2.04% | 43.7% | -0.95% |
| 90-94 | 362 | 36.6% | -2.62% | 39.9% | -3.48% | 48.9% | 0.86% |
| 85-89 | 254 | 41.7% | -1.29% | 45.7% | -2.24% | 48.4% | -2.66% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 177 | 39.8% | -0.97% | 42.0% | -2.07% | 54.0% | 1.41% |
| lifted (0..+5) | 669 | 35.9% | -2.77% | 37.7% | -3.25% | 49.8% | -0.48% |
| extended (>+5) | 1066 | 36.7% | -2.83% | 36.8% | -5.02% | 37.0% | -5.28% |
| pullback (-5..-2) | 117 | 30.8% | -4.08% | 38.5% | -4.68% | 53.8% | 3.74% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.15% | 63.4% | 8.53% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 828 | 38.3% | -2.3% | 43.2% | -2.84% | 46.9% | -1.46% |
| 30-49% | 857 | 36.6% | -2.51% | 36.6% | -3.98% | 42.1% | -2.46% |
| 50+% | 415 | 32.0% | -4.11% | 31.2% | -6.74% | 44.3% | -3.04% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 7.05% |
| Retail Trade | 52 | 51.9% | 3.42% |
| Health Technology | 861 | 55.7% | 2.28% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 19 | 33.3% | -0.58% |
| Technology Services | 413 | 45.9% | -2.02% |
| Finance | 73 | 49.3% | -2.63% |
| Health Services | 60 | 21.7% | -2.67% |
| Transportation | 16 | 31.2% | -3.35% |
| Consumer Services | 37 | 32.4% | -4.02% |
| Non-Energy Minerals | 147 | 21.1% | -8.25% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |
| PSNL | 07-24 | PULLBACK | 94.3 | +23.7% | 11.78 | 18.38 | +56.0% |
| IOVA | 07-22 | EXTENDED | 96.1 | +38.0% | 5.17 | 7.99 | +54.5% |
| ABCL | 07-15 | PULLBACK | 92.6 | +27.2% | 6.74 | 10.35 | +53.6% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| SNDK | 06-30 | TIGHT | 100.0 | +21.9% | 2273.73 | 1015.89 | -55.3% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |
| FCEL | 06-30 | EXTENDED | 99.4 | +23.9% | 36.01 | 18.08 | -49.8% |
| ACMR | 06-30 | EXTENDED | 98.5 | +28.1% | 126.89 | 65.30 | -48.5% |
| ALAB | 06-30 | EXTENDED | 99.1 | +31.0% | 483.02 | 249.74 | -48.3% |
| SNDK | 06-27 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| SNDK | 06-28 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| SNDK | 06-29 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| MRVL | 06-30 | TIGHT | 98.0 | +35.9% | 297.82 | 163.40 | -45.1% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
