# Momentum Scan Performance Audit — 2026-08-28

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2996. With forward data: 2957.

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
| EXTENDED | 1485 | 41.5% | -2.14% | 41.0% | -3.23% | 38.2% | -5.85% |
| TIGHT | 701 | 40.7% | -1.08% | 47.8% | -0.42% | 50.4% | -0.77% |
| BELOW85 | 331 | 41.9% | -0.38% | 51.4% | 1.58% | 57.5% | 3.92% |
| PULLBACK | 291 | 41.3% | -1.0% | 44.4% | -2.32% | 41.0% | -3.42% |
| EARLY | 149 | 33.1% | -4.0% | 33.1% | -5.55% | 45.5% | -6.63% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1619 | 39.0% | -2.49% | 38.8% | -3.36% | 35.1% | -6.88% |
| 90-94 | 533 | 41.6% | -1.19% | 45.9% | -1.47% | 49.9% | -0.45% |
| <85 | 477 | 43.0% | -0.42% | 50.0% | 0.61% | 55.3% | 2.77% |
| 85-89 | 328 | 46.3% | -0.21% | 54.9% | -0.36% | 60.5% | 0.49% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 248 | 39.8% | -0.05% | 52.0% | 2.0% | 56.9% | 3.32% |
| lifted (0..+5) | 857 | 40.5% | -1.55% | 46.2% | -1.15% | 50.9% | -1.21% |
| extended (>+5) | 1485 | 41.5% | -2.14% | 41.0% | -3.23% | 38.2% | -5.85% |
| pullback (-5..-2) | 196 | 41.2% | -1.91% | 45.4% | -0.92% | 51.0% | 1.3% |
| deep-pb (<-5) | 171 | 39.4% | -0.28% | 41.2% | -3.5% | 31.2% | -7.29% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1039 | 42.0% | -1.47% | 46.5% | -1.61% | 46.1% | -2.36% |
| 30-49% | 1158 | 43.6% | -0.56% | 46.8% | -0.47% | 45.7% | -1.7% |
| 50+% | 760 | 35.2% | -3.65% | 35.1% | -5.07% | 37.9% | -7.25% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 14.38% |
| Health Services | 97 | 51.0% | 7.71% |
| Consumer Durables | 5 | 80.0% | 6.52% |
| Health Technology | 947 | 60.2% | 5.86% |
| Retail Trade | 62 | 77.0% | 5.65% |
| Consumer Non-Durables | 13 | 84.6% | 3.68% |
| Energy Minerals | 30 | 63.3% | 3.41% |
| Transportation | 35 | 37.1% | -0.97% |
| Non-Energy Minerals | 101 | 67.7% | -1.22% |
| Consumer Services | 37 | 48.6% | -1.31% |
| Finance | 84 | 44.0% | -2.63% |
| Technology Services | 648 | 45.7% | -4.41% |

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
