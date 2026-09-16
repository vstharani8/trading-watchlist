# Momentum Scan Performance Audit — 2026-09-16

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2328. With forward data: 2320.

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
| EXTENDED | 1179 | 39.1% | -2.29% | 35.3% | -5.63% | 31.2% | -7.51% |
| TIGHT | 589 | 39.5% | -1.58% | 38.4% | -2.95% | 45.1% | -1.24% |
| BELOW85 | 272 | 38.6% | -0.7% | 37.9% | -1.45% | 42.3% | 0.07% |
| PULLBACK | 162 | 30.2% | -4.14% | 38.3% | -6.09% | 48.1% | 1.59% |
| EARLY | 118 | 26.3% | -5.11% | 25.4% | -7.9% | 38.1% | -8.13% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1234 | 35.2% | -3.29% | 31.2% | -6.57% | 34.2% | -6.84% |
| <85 | 415 | 39.5% | -0.85% | 39.8% | -1.94% | 38.8% | -2.1% |
| 90-94 | 406 | 39.5% | -1.68% | 39.8% | -3.59% | 42.0% | -1.22% |
| 85-89 | 265 | 45.3% | 0.01% | 47.5% | -1.25% | 44.5% | -1.75% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 198 | 38.9% | -0.83% | 37.9% | -2.57% | 43.9% | -0.93% |
| lifted (0..+5) | 740 | 36.7% | -2.09% | 36.3% | -3.5% | 43.0% | -2.15% |
| extended (>+5) | 1179 | 39.1% | -2.29% | 35.3% | -5.63% | 31.2% | -7.51% |
| pullback (-5..-2) | 126 | 31.7% | -4.02% | 35.7% | -5.39% | 46.8% | 0.88% |
| deep-pb (<-5) | 77 | 37.7% | -2.33% | 42.9% | -3.54% | 50.6% | 3.2% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 894 | 39.1% | -1.99% | 41.0% | -3.23% | 40.9% | -3.34% |
| 30-49% | 945 | 39.3% | -1.61% | 35.8% | -4.13% | 36.7% | -3.67% |
| 50+% | 481 | 32.8% | -3.73% | 27.6% | -8.11% | 33.3% | -7.93% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 30 | 83.3% | 9.39% |
| Consumer Durables | 2 | 100.0% | 9.0% |
| Retail Trade | 53 | 52.8% | 3.98% |
| Health Technology | 926 | 49.9% | 1.19% |
| Industrial Services | 18 | 33.3% | -0.58% |
| Health Services | 75 | 28.0% | -1.64% |
| Consumer Services | 38 | 31.6% | -4.07% |
| Technology Services | 452 | 42.3% | -4.68% |
| Finance | 76 | 39.5% | -4.95% |
| Transportation | 22 | 22.7% | -7.45% |
| Consumer Non-Durables | 13 | 0.0% | -8.38% |

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
| HQ | 06-19 | EXTENDED | 96.6 | +180.7% | 38.39 | 16.69 | -56.5% |
| HQ | 06-23 | EXTENDED | 98.0 | +215.4% | 33.39 | 14.64 | -56.1% |
| SNDK | 06-30 | TIGHT | 100.0 | +21.9% | 2273.73 | 1015.89 | -55.3% |
| ALOY | 06-24 | EXTENDED | 96.2 | +98.7% | 16.67 | 7.47 | -55.2% |
| ALOY | 06-19 | EXTENDED | 94.3 | +100.2% | 19.70 | 9.00 | -54.3% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |
| ALOY | 06-25 | TIGHT | 95.2 | +72.7% | 14.25 | 7.03 | -50.7% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
