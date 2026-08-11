# Momentum Scan Performance Audit — 2026-08-11

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2576. With forward data: 2576.

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
| EXTENDED | 1264 | 41.2% | -2.56% | 40.0% | -3.4% | 35.7% | -7.37% |
| TIGHT | 632 | 38.2% | -1.39% | 45.3% | -0.63% | 47.4% | -1.33% |
| BELOW85 | 281 | 41.1% | -0.23% | 52.1% | 1.87% | 60.4% | 4.52% |
| PULLBACK | 271 | 40.7% | -1.1% | 43.7% | -2.48% | 37.4% | -5.04% |
| EARLY | 128 | 29.9% | -4.57% | 29.9% | -6.01% | 43.3% | -7.28% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1442 | 38.5% | -2.81% | 39.6% | -3.39% | 34.3% | -7.81% |
| 90-94 | 473 | 40.8% | -1.17% | 41.4% | -1.79% | 45.9% | -1.57% |
| <85 | 391 | 42.1% | -0.53% | 50.6% | 1.15% | 57.4% | 2.73% |
| 85-89 | 270 | 42.0% | -0.79% | 48.5% | -1.08% | 52.7% | -0.6% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 226 | 37.6% | -0.24% | 49.6% | 2.16% | 50.9% | 2.99% |
| lifted (0..+5) | 742 | 38.0% | -1.83% | 44.4% | -1.41% | 50.6% | -1.59% |
| extended (>+5) | 1264 | 41.2% | -2.56% | 40.0% | -3.4% | 35.7% | -7.37% |
| pullback (-5..-2) | 183 | 41.0% | -2.09% | 45.4% | -0.97% | 48.6% | 0.4% |
| deep-pb (<-5) | 161 | 39.4% | -0.17% | 40.6% | -3.6% | 28.7% | -8.95% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 899 | 41.0% | -1.76% | 46.0% | -1.87% | 45.3% | -3.44% |
| 30-49% | 984 | 43.0% | -0.59% | 45.5% | -0.26% | 43.3% | -2.42% |
| 50+% | 693 | 34.0% | -4.13% | 34.1% | -5.21% | 35.4% | -8.08% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Services | 86 | 55.3% | 8.54% |
| Commercial Services | 19 | 84.2% | 7.3% |
| Consumer Durables | 5 | 80.0% | 6.48% |
| Retail Trade | 59 | 72.9% | 5.61% |
| Energy Minerals | 22 | 81.0% | 4.38% |
| Health Technology | 845 | 56.1% | 4.34% |
| Consumer Non-Durables | 3 | 50.0% | 3.78% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 44.0% | -2.7% |
| Technology Services | 546 | 44.2% | -4.67% |
| Consumer Services | 31 | 20.0% | -7.61% |
| Miscellaneous | 5 | 20.0% | -11.97% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| SLS | 06-06 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-07 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-08 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-12 | PULLBACK | 98.8 | +48.5% | 7.83 | 13.39 | +71.0% |
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 9.76 | +68.3% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 9.76 | +68.3% |

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
