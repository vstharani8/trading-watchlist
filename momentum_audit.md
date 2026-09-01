# Momentum Scan Performance Audit — 2026-09-01

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2972. With forward data: 2939.

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
| EXTENDED | 1442 | 41.4% | -1.69% | 39.5% | -3.42% | 35.3% | -6.5% |
| TIGHT | 713 | 40.6% | -0.91% | 46.1% | -0.59% | 48.4% | -0.97% |
| BELOW85 | 344 | 39.8% | -0.45% | 48.9% | 1.15% | 55.0% | 3.41% |
| PULLBACK | 291 | 40.0% | -1.06% | 42.8% | -2.61% | 38.9% | -3.49% |
| EARLY | 149 | 30.6% | -3.96% | 30.6% | -5.92% | 42.9% | -6.87% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1594 | 38.9% | -2.2% | 37.3% | -3.75% | 33.2% | -7.47% |
| 90-94 | 535 | 41.1% | -0.95% | 45.1% | -1.44% | 47.4% | -0.71% |
| <85 | 491 | 40.2% | -0.46% | 46.4% | 0.28% | 51.1% | 2.37% |
| 85-89 | 319 | 46.5% | 0.31% | 54.2% | 0.01% | 58.3% | 0.56% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 255 | 39.4% | -0.06% | 49.8% | 1.65% | 54.6% | 2.92% |
| lifted (0..+5) | 872 | 39.3% | -1.43% | 44.0% | -1.43% | 48.5% | -1.51% |
| extended (>+5) | 1442 | 41.4% | -1.69% | 39.5% | -3.42% | 35.3% | -6.5% |
| pullback (-5..-2) | 198 | 39.9% | -1.97% | 43.5% | -1.11% | 48.7% | 1.33% |
| deep-pb (<-5) | 172 | 38.7% | -0.36% | 40.5% | -3.82% | 30.4% | -7.52% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1040 | 40.5% | -1.45% | 44.2% | -2.02% | 42.5% | -3.29% |
| 30-49% | 1164 | 42.3% | -0.45% | 44.1% | -0.79% | 42.5% | -2.08% |
| 50+% | 735 | 37.0% | -2.89% | 35.7% | -4.93% | 38.4% | -7.05% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 14.72% |
| Health Services | 98 | 49.0% | 7.36% |
| Consumer Durables | 5 | 80.0% | 7.15% |
| Energy Minerals | 30 | 76.7% | 6.54% |
| Consumer Non-Durables | 13 | 100.0% | 5.33% |
| Retail Trade | 64 | 69.4% | 5.05% |
| Health Technology | 966 | 56.7% | 4.78% |
| Transportation | 34 | 35.3% | -1.97% |
| Consumer Services | 37 | 43.2% | -2.41% |
| Finance | 83 | 42.2% | -3.22% |
| Technology Services | 642 | 44.5% | -4.33% |
| Non-Energy Minerals | 115 | 33.7% | -6.17% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| NLST | 08-06 | EXTENDED | 0.0 | +31.2% | 3.82 | 6.82 | +78.5% |
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
| ALOY | 06-18 | EXTENDED | 92.8 | +95.0% | 17.78 | 8.40 | -52.8% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 255.43 | 124.05 | -51.4% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
