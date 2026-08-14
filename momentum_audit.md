# Momentum Scan Performance Audit — 2026-08-14

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2594. With forward data: 2563.

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
| EXTENDED | 1264 | 41.9% | -2.29% | 39.5% | -3.38% | 35.5% | -7.11% |
| TIGHT | 626 | 38.6% | -1.36% | 45.3% | -0.83% | 48.6% | -1.14% |
| BELOW85 | 280 | 40.6% | -0.44% | 51.4% | 1.57% | 59.7% | 4.7% |
| PULLBACK | 267 | 41.9% | -0.83% | 44.6% | -2.3% | 40.1% | -3.83% |
| EARLY | 126 | 28.6% | -4.59% | 29.4% | -6.45% | 42.9% | -7.38% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1432 | 39.2% | -2.61% | 39.7% | -3.26% | 35.0% | -7.53% |
| 90-94 | 470 | 40.8% | -1.21% | 41.0% | -2.18% | 46.2% | -1.39% |
| <85 | 385 | 40.8% | -0.52% | 48.2% | 0.73% | 55.5% | 3.18% |
| 85-89 | 276 | 44.2% | -0.54% | 49.8% | -1.27% | 54.3% | -0.16% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 220 | 38.4% | -0.37% | 49.3% | 1.67% | 53.4% | 3.1% |
| lifted (0..+5) | 739 | 37.7% | -1.84% | 44.1% | -1.6% | 50.5% | -1.42% |
| extended (>+5) | 1264 | 41.9% | -2.29% | 39.5% | -3.38% | 35.5% | -7.11% |
| pullback (-5..-2) | 182 | 41.2% | -2.02% | 45.1% | -0.92% | 50.0% | 1.45% |
| deep-pb (<-5) | 158 | 41.1% | 0.2% | 42.4% | -3.37% | 31.6% | -7.94% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 914 | 40.9% | -1.64% | 45.1% | -1.86% | 44.5% | -2.97% |
| 30-49% | 990 | 44.1% | -0.39% | 45.8% | -0.28% | 44.2% | -2.13% |
| 50+% | 659 | 33.7% | -4.18% | 33.3% | -5.71% | 36.0% | -8.21% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 10.88% |
| Energy Minerals | 24 | 82.6% | 9.72% |
| Health Services | 88 | 55.2% | 8.64% |
| Consumer Durables | 5 | 100.0% | 8.39% |
| Retail Trade | 58 | 74.1% | 5.75% |
| Health Technology | 851 | 56.5% | 4.27% |
| Consumer Non-Durables | 4 | 100.0% | 3.34% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 83 | 43.4% | -2.23% |
| Consumer Services | 33 | 34.4% | -3.82% |
| Technology Services | 542 | 45.0% | -3.89% |
| Process Industries | 4 | 0.0% | -5.8% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 10.97 | +89.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 10.97 | +89.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 10.97 | +89.1% |
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
