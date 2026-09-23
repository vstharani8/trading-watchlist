# Momentum Scan Performance Audit — 2026-09-23

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2144. With forward data: 2109.

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
| EXTENDED | 1065 | 37.4% | -2.81% | 36.8% | -5.17% | 37.4% | -5.6% |
| TIGHT | 535 | 40.3% | -1.78% | 41.5% | -2.24% | 54.8% | 1.39% |
| BELOW85 | 253 | 36.0% | -1.89% | 41.5% | -1.55% | 46.2% | 1.3% |
| PULLBACK | 150 | 28.0% | -4.65% | 39.3% | -5.68% | 54.7% | 5.16% |
| EARLY | 106 | 26.0% | -5.67% | 23.1% | -7.86% | 42.3% | -6.9% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1094 | 35.7% | -3.4% | 34.2% | -5.56% | 41.9% | -3.84% |
| <85 | 391 | 35.9% | -1.94% | 42.6% | -2.04% | 43.2% | -0.83% |
| 90-94 | 365 | 36.8% | -2.56% | 39.8% | -3.56% | 49.5% | 0.78% |
| 85-89 | 259 | 42.2% | -1.17% | 45.3% | -2.24% | 49.6% | -2.21% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 180 | 40.6% | -0.91% | 42.2% | -2.08% | 51.1% | 1.24% |
| lifted (0..+5) | 675 | 35.9% | -2.71% | 37.6% | -3.22% | 49.8% | -0.22% |
| extended (>+5) | 1065 | 37.4% | -2.81% | 36.8% | -5.17% | 37.4% | -5.6% |
| pullback (-5..-2) | 118 | 29.7% | -4.08% | 38.1% | -4.5% | 54.2% | 3.99% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.74% | 63.4% | 8.15% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 829 | 38.7% | -2.24% | 43.1% | -2.86% | 46.7% | -1.67% |
| 30-49% | 857 | 36.9% | -2.47% | 36.8% | -3.97% | 42.6% | -2.11% |
| 50+% | 423 | 32.5% | -4.13% | 30.8% | -7.06% | 43.6% | -3.82% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 7.19% |
| Retail Trade | 52 | 57.7% | 4.08% |
| Health Technology | 873 | 55.0% | 2.06% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 18 | 33.3% | -0.58% |
| Technology Services | 408 | 50.1% | -1.57% |
| Health Services | 62 | 21.0% | -2.87% |
| Finance | 71 | 50.0% | -3.01% |
| Consumer Services | 37 | 32.4% | -4.01% |
| Transportation | 17 | 29.4% | -4.46% |
| Non-Energy Minerals | 147 | 17.0% | -7.06% |

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
