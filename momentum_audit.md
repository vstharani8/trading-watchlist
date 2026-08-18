# Momentum Scan Performance Audit — 2026-08-18

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2719. With forward data: 2594.

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
| EXTENDED | 1289 | 42.8% | -1.89% | 40.5% | -3.02% | 36.2% | -6.65% |
| TIGHT | 629 | 38.3% | -1.42% | 44.9% | -0.95% | 46.8% | -1.46% |
| BELOW85 | 283 | 40.7% | -0.46% | 51.4% | 1.54% | 58.6% | 4.39% |
| PULLBACK | 267 | 41.9% | -0.9% | 44.6% | -2.38% | 40.1% | -3.88% |
| EARLY | 126 | 28.6% | -4.59% | 29.4% | -6.5% | 42.9% | -7.54% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1447 | 39.8% | -2.38% | 40.2% | -3.09% | 35.3% | -7.31% |
| 90-94 | 478 | 40.2% | -1.25% | 40.2% | -2.27% | 43.6% | -1.59% |
| <85 | 390 | 42.6% | -0.11% | 50.4% | 1.16% | 56.9% | 3.4% |
| 85-89 | 279 | 43.5% | -0.66% | 48.6% | -1.45% | 52.9% | -0.61% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 222 | 37.7% | -0.46% | 48.6% | 1.55% | 51.8% | 2.82% |
| lifted (0..+5) | 743 | 37.8% | -1.87% | 44.0% | -1.68% | 49.1% | -1.72% |
| extended (>+5) | 1289 | 42.8% | -1.89% | 40.5% | -3.02% | 36.2% | -6.65% |
| pullback (-5..-2) | 182 | 41.2% | -2.06% | 45.1% | -0.96% | 50.0% | 1.43% |
| deep-pb (<-5) | 158 | 41.1% | 0.13% | 42.4% | -3.46% | 31.6% | -8.09% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 925 | 41.9% | -1.48% | 46.2% | -1.79% | 44.3% | -2.96% |
| 30-49% | 1002 | 43.7% | -0.23% | 45.3% | -0.14% | 43.5% | -2.04% |
| 50+% | 667 | 34.4% | -4.01% | 33.8% | -5.56% | 36.4% | -8.12% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 9.69% |
| Health Services | 88 | 55.7% | 8.33% |
| Consumer Durables | 5 | 100.0% | 8.04% |
| Energy Minerals | 25 | 79.2% | 6.69% |
| Retail Trade | 58 | 74.1% | 5.78% |
| Health Technology | 857 | 55.1% | 4.24% |
| Consumer Non-Durables | 5 | 75.0% | 1.47% |
| Process Industries | 4 | 25.0% | -0.68% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 43.4% | -2.4% |
| Technology Services | 553 | 43.4% | -4.46% |
| Consumer Services | 34 | 27.3% | -5.88% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.38 | +96.2% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.38 | +96.2% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.38 | +96.2% |
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| SLS | 06-06 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-07 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |

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
