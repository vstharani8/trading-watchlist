# Momentum Scan Performance Audit — 2026-08-12

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2525. With forward data: 2525.

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
| EXTENDED | 1232 | 42.1% | -2.29% | 39.6% | -3.55% | 35.4% | -7.43% |
| TIGHT | 622 | 38.3% | -1.41% | 45.0% | -0.92% | 46.1% | -1.48% |
| BELOW85 | 278 | 40.6% | -0.47% | 51.4% | 1.49% | 59.8% | 4.01% |
| PULLBACK | 267 | 41.9% | -0.94% | 44.6% | -2.4% | 39.7% | -4.34% |
| EARLY | 126 | 29.4% | -4.6% | 30.2% | -6.51% | 42.9% | -7.71% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1413 | 39.7% | -2.57% | 40.1% | -3.3% | 35.0% | -7.67% |
| 90-94 | 463 | 39.9% | -1.32% | 40.1% | -2.35% | 43.2% | -1.85% |
| <85 | 380 | 42.1% | -0.49% | 49.3% | 0.57% | 56.8% | 2.53% |
| 85-89 | 269 | 42.0% | -0.81% | 47.7% | -1.61% | 52.3% | -0.99% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 219 | 38.1% | -0.43% | 49.1% | 1.57% | 52.3% | 2.8% |
| lifted (0..+5) | 734 | 37.7% | -1.89% | 44.0% | -1.69% | 48.8% | -1.88% |
| extended (>+5) | 1232 | 42.1% | -2.29% | 39.6% | -3.55% | 35.4% | -7.43% |
| pullback (-5..-2) | 182 | 41.2% | -2.09% | 45.1% | -0.99% | 49.5% | 0.73% |
| deep-pb (<-5) | 158 | 41.1% | 0.11% | 42.4% | -3.46% | 31.6% | -8.31% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 898 | 42.1% | -1.59% | 46.4% | -1.92% | 45.4% | -3.34% |
| 30-49% | 972 | 43.3% | -0.46% | 44.9% | -0.43% | 43.0% | -2.48% |
| 50+% | 655 | 33.6% | -4.21% | 33.0% | -5.79% | 34.6% | -8.51% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Services | 87 | 54.7% | 8.52% |
| Consumer Durables | 5 | 80.0% | 7.34% |
| Commercial Services | 19 | 84.2% | 6.2% |
| Retail Trade | 58 | 74.1% | 5.84% |
| Process Industries | 3 | 100.0% | 5.26% |
| Energy Minerals | 23 | 72.7% | 5.0% |
| Health Technology | 843 | 56.6% | 4.48% |
| Consumer Non-Durables | 3 | 100.0% | 0.63% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 83 | 43.4% | -2.67% |
| Consumer Services | 32 | 32.3% | -5.37% |
| Technology Services | 533 | 41.4% | -5.5% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 10.35 | +78.5% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 10.35 | +78.5% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 10.35 | +78.5% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| SLS | 06-06 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-07 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-08 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |

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
