# Momentum Scan Performance Audit — 2026-09-21

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2216. With forward data: 2200.

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
| EXTENDED | 1101 | 37.8% | -2.65% | 36.7% | -5.07% | 35.8% | -6.11% |
| TIGHT | 569 | 39.8% | -1.83% | 40.3% | -2.55% | 49.6% | -0.19% |
| BELOW85 | 261 | 37.7% | -1.35% | 41.5% | -1.14% | 47.3% | 1.28% |
| PULLBACK | 158 | 27.8% | -4.73% | 38.6% | -6.16% | 48.7% | 2.6% |
| EARLY | 111 | 26.1% | -5.5% | 25.2% | -7.47% | 41.4% | -7.42% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1157 | 35.1% | -3.45% | 34.1% | -5.66% | 39.2% | -5.09% |
| <85 | 398 | 37.5% | -1.51% | 41.3% | -1.84% | 42.6% | -0.93% |
| 90-94 | 382 | 38.0% | -2.1% | 40.3% | -3.39% | 46.9% | 0.09% |
| 85-89 | 263 | 42.9% | -1.04% | 44.8% | -2.15% | 46.4% | -2.63% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 191 | 39.8% | -1.09% | 41.4% | -2.41% | 49.2% | 0.01% |
| lifted (0..+5) | 710 | 36.3% | -2.5% | 37.6% | -3.16% | 47.0% | -1.14% |
| extended (>+5) | 1101 | 37.8% | -2.65% | 36.7% | -5.07% | 35.8% | -6.11% |
| pullback (-5..-2) | 124 | 29.8% | -4.08% | 37.1% | -4.88% | 47.6% | 1.73% |
| deep-pb (<-5) | 74 | 36.5% | -3.54% | 47.3% | -3.3% | 56.8% | 5.4% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 862 | 38.6% | -2.17% | 42.0% | -2.96% | 44.1% | -2.54% |
| 30-49% | 897 | 37.8% | -2.22% | 37.4% | -3.73% | 40.4% | -2.65% |
| 50+% | 441 | 32.0% | -4.1% | 30.2% | -7.36% | 41.2% | -5.27% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 78.1% | 7.75% |
| Retail Trade | 52 | 51.9% | 3.86% |
| Health Technology | 903 | 53.4% | 1.48% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 18 | 33.3% | -0.58% |
| Health Services | 69 | 24.6% | -2.36% |
| Technology Services | 422 | 44.8% | -3.14% |
| Consumer Services | 38 | 34.2% | -3.61% |
| Finance | 73 | 46.6% | -3.74% |
| Transportation | 19 | 26.3% | -6.83% |
| Non-Energy Minerals | 149 | 22.8% | -7.03% |

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
| ALOY | 06-24 | EXTENDED | 96.2 | +98.7% | 16.67 | 7.47 | -55.2% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |
| ALOY | 06-25 | TIGHT | 95.2 | +72.7% | 14.25 | 7.03 | -50.7% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |
| FCEL | 06-30 | EXTENDED | 99.4 | +23.9% | 36.01 | 18.08 | -49.8% |
| ACMR | 06-30 | EXTENDED | 98.5 | +28.1% | 126.89 | 65.30 | -48.5% |
| ALAB | 06-30 | EXTENDED | 99.1 | +31.0% | 483.02 | 249.74 | -48.3% |
| SNDK | 06-27 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
