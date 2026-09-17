# Momentum Scan Performance Audit — 2026-09-17

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2248. With forward data: 2241.

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
| EXTENDED | 1131 | 38.9% | -2.28% | 35.9% | -5.29% | 32.7% | -6.93% |
| TIGHT | 574 | 39.9% | -1.58% | 40.0% | -2.76% | 47.4% | -0.96% |
| BELOW85 | 265 | 38.5% | -1.03% | 38.1% | -1.85% | 43.4% | -0.25% |
| PULLBACK | 158 | 28.5% | -4.85% | 36.7% | -6.58% | 46.2% | 1.46% |
| EARLY | 113 | 27.4% | -5.06% | 25.7% | -7.45% | 40.7% | -7.6% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1185 | 35.5% | -3.27% | 32.5% | -6.1% | 36.3% | -6.2% |
| <85 | 403 | 38.6% | -1.23% | 39.1% | -2.4% | 39.3% | -2.4% |
| 90-94 | 391 | 39.0% | -1.76% | 40.0% | -3.39% | 43.6% | -0.66% |
| 85-89 | 262 | 45.4% | -0.15% | 47.7% | -1.58% | 44.6% | -1.91% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 194 | 39.9% | -0.81% | 39.9% | -2.56% | 46.1% | -0.95% |
| lifted (0..+5) | 717 | 36.7% | -2.21% | 37.0% | -3.45% | 45.0% | -1.97% |
| extended (>+5) | 1131 | 38.9% | -2.28% | 35.9% | -5.29% | 32.7% | -6.93% |
| pullback (-5..-2) | 124 | 30.6% | -4.16% | 34.7% | -5.54% | 45.2% | 0.8% |
| deep-pb (<-5) | 75 | 37.3% | -3.48% | 42.7% | -4.0% | 50.7% | 3.32% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 873 | 39.1% | -2.02% | 41.2% | -3.13% | 41.6% | -3.12% |
| 30-49% | 915 | 39.2% | -1.73% | 36.1% | -4.09% | 37.7% | -3.57% |
| 50+% | 453 | 32.4% | -3.87% | 29.3% | -7.66% | 37.1% | -6.82% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 31 | 80.0% | 8.8% |
| Retail Trade | 52 | 53.8% | 4.29% |
| Health Technology | 911 | 51.4% | 1.21% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 18 | 33.3% | -0.58% |
| Health Services | 73 | 26.0% | -2.06% |
| Consumer Services | 38 | 31.6% | -3.95% |
| Technology Services | 432 | 42.6% | -4.22% |
| Finance | 74 | 39.2% | -5.25% |
| Transportation | 20 | 25.0% | -7.38% |
| Consumer Non-Durables | 13 | 0.0% | -9.58% |

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
| ALOY | 06-23 | EXTENDED | 96.1 | +104.1% | 19.17 | 8.19 | -57.3% |
| HQ | 06-23 | EXTENDED | 98.0 | +215.4% | 33.39 | 14.64 | -56.1% |
| SNDK | 06-30 | TIGHT | 100.0 | +21.9% | 2273.73 | 1015.89 | -55.3% |
| ALOY | 06-24 | EXTENDED | 96.2 | +98.7% | 16.67 | 7.47 | -55.2% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |
| ALOY | 06-25 | TIGHT | 95.2 | +72.7% | 14.25 | 7.03 | -50.7% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |
| FCEL | 06-30 | EXTENDED | 99.4 | +23.9% | 36.01 | 18.08 | -49.8% |
| ACMR | 06-30 | EXTENDED | 98.5 | +28.1% | 126.89 | 65.30 | -48.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
