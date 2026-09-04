# Momentum Scan Performance Audit — 2026-09-04

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2837. With forward data: 2809.

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
| EXTENDED | 1346 | 43.1% | -1.42% | 41.3% | -3.54% | 36.9% | -6.44% |
| TIGHT | 704 | 42.9% | -0.74% | 46.7% | -0.68% | 50.7% | -0.62% |
| BELOW85 | 351 | 45.0% | 0.08% | 56.8% | 1.75% | 65.3% | 4.48% |
| PULLBACK | 267 | 42.5% | -1.19% | 44.7% | -2.92% | 43.6% | -2.28% |
| EARLY | 141 | 30.9% | -4.09% | 31.7% | -6.56% | 43.9% | -7.3% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1510 | 40.1% | -2.1% | 37.3% | -4.16% | 35.3% | -7.07% |
| 90-94 | 504 | 43.5% | -0.55% | 47.3% | -1.14% | 47.5% | -0.1% |
| <85 | 490 | 45.6% | 0.04% | 55.6% | 0.96% | 60.7% | 2.53% |
| 85-89 | 305 | 48.8% | 0.45% | 56.8% | 0.1% | 62.0% | 0.93% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 255 | 43.0% | 0.32% | 52.2% | 1.89% | 57.4% | 2.94% |
| lifted (0..+5) | 856 | 41.5% | -1.22% | 46.5% | -1.46% | 53.0% | -0.9% |
| extended (>+5) | 1346 | 43.1% | -1.42% | 41.3% | -3.54% | 36.9% | -6.44% |
| pullback (-5..-2) | 193 | 42.5% | -2.07% | 45.6% | -1.61% | 53.4% | 1.81% |
| deep-pb (<-5) | 159 | 44.2% | -0.14% | 45.5% | -3.19% | 37.8% | -5.41% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1025 | 42.2% | -1.36% | 45.7% | -2.04% | 45.7% | -3.0% |
| 30-49% | 1139 | 44.8% | -0.25% | 47.4% | -0.71% | 46.9% | -1.54% |
| 50+% | 645 | 39.4% | -2.52% | 36.9% | -5.39% | 39.6% | -6.86% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 17 | 100.0% | 13.08% |
| Energy Minerals | 29 | 82.8% | 8.63% |
| Consumer Durables | 5 | 100.0% | 7.63% |
| Health Services | 96 | 48.4% | 6.33% |
| Retail Trade | 64 | 68.3% | 4.64% |
| Consumer Non-Durables | 13 | 84.6% | 4.37% |
| Health Technology | 976 | 57.7% | 4.25% |
| Non-Energy Minerals | 141 | 68.7% | -1.38% |
| Finance | 83 | 42.7% | -3.67% |
| Consumer Services | 37 | 37.8% | -3.82% |
| Technology Services | 594 | 46.8% | -3.89% |
| Transportation | 31 | 29.0% | -4.64% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| SLS | 06-07 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-08 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-12 | PULLBACK | 98.8 | +48.5% | 7.83 | 13.39 | +71.0% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ALOY | 06-23 | EXTENDED | 96.1 | +104.1% | 19.17 | 8.19 | -57.3% |
| HQ | 06-19 | EXTENDED | 96.6 | +180.7% | 38.39 | 16.69 | -56.5% |
| HYLN | 06-18 | EXTENDED | 99.4 | +68.4% | 8.10 | 3.55 | -56.2% |
| HQ | 06-23 | EXTENDED | 98.0 | +215.4% | 33.39 | 14.64 | -56.1% |
| SNDK | 06-30 | TIGHT | 100.0 | +21.9% | 2273.73 | 1015.89 | -55.3% |
| ALOY | 06-24 | EXTENDED | 96.2 | +98.7% | 16.67 | 7.47 | -55.2% |
| ALOY | 06-19 | EXTENDED | 94.3 | +100.2% | 19.70 | 9.00 | -54.3% |
| ALOY | 06-18 | EXTENDED | 92.8 | +95.0% | 17.78 | 8.40 | -52.8% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
