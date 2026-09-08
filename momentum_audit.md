# Momentum Scan Performance Audit — 2026-09-08

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2670. With forward data: 2630.

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
| EXTENDED | 1321 | 41.8% | -1.59% | 40.2% | -3.87% | 34.5% | -6.96% |
| TIGHT | 662 | 42.6% | -0.93% | 44.8% | -1.04% | 49.2% | -1.32% |
| BELOW85 | 320 | 40.3% | -0.23% | 53.4% | 2.07% | 62.0% | 4.41% |
| PULLBACK | 194 | 36.6% | -3.11% | 41.8% | -3.79% | 45.4% | 0.02% |
| EARLY | 133 | 28.2% | -4.55% | 26.0% | -7.97% | 39.7% | -9.06% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1413 | 38.1% | -2.63% | 35.3% | -4.72% | 34.5% | -7.28% |
| 90-94 | 467 | 43.6% | -0.54% | 47.3% | -1.28% | 46.2% | -0.65% |
| <85 | 460 | 41.2% | -0.3% | 51.2% | 0.86% | 55.4% | 1.77% |
| 85-89 | 290 | 48.6% | 0.37% | 54.9% | -0.22% | 55.6% | -0.25% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 232 | 42.8% | 0.47% | 51.1% | 2.04% | 56.8% | 2.41% |
| lifted (0..+5) | 819 | 39.6% | -1.55% | 43.2% | -2.04% | 49.8% | -1.78% |
| extended (>+5) | 1321 | 41.8% | -1.59% | 40.2% | -3.87% | 34.5% | -6.96% |
| pullback (-5..-2) | 159 | 33.5% | -3.34% | 40.5% | -2.05% | 50.0% | 2.07% |
| deep-pb (<-5) | 99 | 43.4% | -2.08% | 46.5% | -3.2% | 46.5% | -1.16% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 977 | 41.6% | -1.56% | 45.0% | -2.15% | 45.1% | -3.04% |
| 30-49% | 1089 | 42.4% | -0.62% | 44.5% | -1.28% | 43.0% | -2.22% |
| 50+% | 564 | 36.3% | -3.2% | 33.6% | -6.12% | 37.2% | -7.98% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 100.0% | 12.2% |
| Energy Minerals | 29 | 79.3% | 8.05% |
| Consumer Durables | 5 | 100.0% | 7.63% |
| Retail Trade | 61 | 70.0% | 5.35% |
| Health Services | 89 | 48.9% | 4.47% |
| Health Technology | 962 | 56.0% | 3.3% |
| Industrial Services | 18 | 33.3% | 0.98% |
| Consumer Non-Durables | 13 | 46.2% | -0.98% |
| Consumer Services | 37 | 40.5% | -2.61% |
| Non-Energy Minerals | 147 | 49.6% | -2.78% |
| Finance | 80 | 40.5% | -4.38% |
| Technology Services | 540 | 41.5% | -5.28% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| SLS | 06-12 | PULLBACK | 98.8 | +48.5% | 7.83 | 13.39 | +71.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| SLS | 06-13 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-14 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-15 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |

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
