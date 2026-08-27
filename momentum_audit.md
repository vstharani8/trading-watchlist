# Momentum Scan Performance Audit — 2026-08-27

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2957. With forward data: 2925.

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
| EXTENDED | 1470 | 40.5% | -2.24% | 39.0% | -3.63% | 35.9% | -6.59% |
| TIGHT | 695 | 39.6% | -1.25% | 45.4% | -0.73% | 47.9% | -1.12% |
| BELOW85 | 327 | 40.2% | -0.64% | 48.9% | 1.14% | 55.4% | 3.45% |
| PULLBACK | 288 | 41.1% | -1.14% | 43.9% | -2.53% | 40.4% | -3.64% |
| EARLY | 145 | 33.3% | -4.12% | 33.3% | -5.99% | 45.8% | -7.18% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1602 | 38.7% | -2.55% | 38.2% | -3.56% | 34.6% | -7.21% |
| 90-94 | 529 | 40.7% | -1.32% | 42.8% | -1.96% | 45.6% | -1.2% |
| <85 | 470 | 40.6% | -0.72% | 46.2% | 0.07% | 51.8% | 1.98% |
| 85-89 | 324 | 44.5% | -0.46% | 51.7% | -1.04% | 57.4% | -0.44% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 246 | 38.0% | -0.26% | 48.3% | 1.66% | 53.3% | 2.94% |
| lifted (0..+5) | 845 | 39.5% | -1.75% | 44.4% | -1.55% | 49.2% | -1.67% |
| extended (>+5) | 1470 | 40.5% | -2.24% | 39.0% | -3.63% | 35.9% | -6.59% |
| pullback (-5..-2) | 194 | 40.8% | -2.04% | 44.5% | -1.09% | 50.3% | 1.18% |
| deep-pb (<-5) | 170 | 39.4% | -0.4% | 41.2% | -3.63% | 31.2% | -7.46% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1030 | 41.2% | -1.55% | 44.8% | -1.93% | 44.4% | -2.94% |
| 30-49% | 1146 | 42.5% | -0.73% | 44.3% | -0.89% | 42.9% | -2.33% |
| 50+% | 749 | 34.5% | -3.81% | 33.8% | -5.43% | 36.7% | -7.67% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 13.93% |
| Health Services | 96 | 53.7% | 8.07% |
| Consumer Durables | 5 | 80.0% | 6.81% |
| Health Technology | 934 | 60.3% | 5.89% |
| Retail Trade | 61 | 76.7% | 5.71% |
| Consumer Non-Durables | 13 | 100.0% | 4.88% |
| Energy Minerals | 30 | 63.3% | 3.51% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 42.9% | -2.64% |
| Consumer Services | 37 | 43.2% | -2.75% |
| Non-Energy Minerals | 96 | 53.8% | -3.92% |
| Technology Services | 641 | 39.7% | -5.86% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| SLS | 06-06 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |

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
| NVTS | 06-03 | TIGHT | 98.5 | +57.2% | 30.84 | 14.46 | -53.1% |
| ALOY | 06-18 | EXTENDED | 92.8 | +95.0% | 17.78 | 8.40 | -52.8% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
