# Momentum Scan Performance Audit — 2026-09-22

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2177. With forward data: 2160.

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
| EXTENDED | 1091 | 38.1% | -2.64% | 37.4% | -5.01% | 37.3% | -5.65% |
| TIGHT | 553 | 39.4% | -2.1% | 41.0% | -2.44% | 53.2% | 0.68% |
| BELOW85 | 255 | 36.5% | -1.75% | 42.0% | -1.41% | 46.7% | 1.42% |
| PULLBACK | 154 | 27.9% | -4.86% | 39.0% | -5.88% | 53.2% | 4.23% |
| EARLY | 107 | 26.7% | -5.6% | 22.9% | -7.82% | 41.9% | -7.08% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1127 | 35.6% | -3.5% | 34.4% | -5.54% | 41.2% | -4.22% |
| <85 | 395 | 36.6% | -1.8% | 43.0% | -1.96% | 43.5% | -0.8% |
| 90-94 | 374 | 37.0% | -2.47% | 39.7% | -3.56% | 48.5% | 0.47% |
| 85-89 | 264 | 43.3% | -0.96% | 46.0% | -2.08% | 49.4% | -2.28% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 186 | 39.2% | -1.47% | 40.9% | -2.48% | 49.5% | 0.57% |
| lifted (0..+5) | 689 | 35.8% | -2.77% | 37.7% | -3.22% | 49.1% | -0.6% |
| extended (>+5) | 1091 | 38.1% | -2.64% | 37.4% | -5.01% | 37.3% | -5.65% |
| pullback (-5..-2) | 122 | 30.3% | -4.05% | 38.5% | -4.46% | 53.3% | 3.3% |
| deep-pb (<-5) | 72 | 36.1% | -3.82% | 50.0% | -3.06% | 62.5% | 7.53% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 848 | 38.8% | -2.31% | 42.9% | -2.94% | 45.8% | -2.03% |
| 30-49% | 879 | 37.3% | -2.43% | 37.4% | -3.85% | 42.4% | -2.26% |
| 50+% | 433 | 32.6% | -4.01% | 31.2% | -6.96% | 43.1% | -4.11% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 7.19% |
| Retail Trade | 52 | 57.7% | 4.08% |
| Health Technology | 890 | 54.6% | 1.94% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 18 | 33.3% | -0.58% |
| Technology Services | 417 | 49.5% | -1.86% |
| Health Services | 65 | 21.5% | -2.85% |
| Finance | 73 | 48.6% | -3.28% |
| Consumer Services | 38 | 34.2% | -3.6% |
| Transportation | 18 | 27.8% | -5.76% |
| Non-Energy Minerals | 148 | 16.9% | -7.36% |

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
| ALOY | 06-25 | TIGHT | 95.2 | +72.7% | 14.25 | 7.03 | -50.7% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |
| FCEL | 06-30 | EXTENDED | 99.4 | +23.9% | 36.01 | 18.08 | -49.8% |
| ACMR | 06-30 | EXTENDED | 98.5 | +28.1% | 126.89 | 65.30 | -48.5% |
| ALAB | 06-30 | EXTENDED | 99.1 | +31.0% | 483.02 | 249.74 | -48.3% |
| SNDK | 06-27 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| SNDK | 06-28 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| SNDK | 06-29 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
