# Momentum Scan Performance Audit — 2026-09-07

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2698. With forward data: 2678.

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
| EXTENDED | 1331 | 42.1% | -1.56% | 40.6% | -3.7% | 34.9% | -6.75% |
| TIGHT | 676 | 43.2% | -0.76% | 45.6% | -0.79% | 49.7% | -1.08% |
| BELOW85 | 329 | 40.4% | -0.29% | 52.8% | 1.89% | 61.5% | 4.32% |
| PULLBACK | 208 | 39.9% | -2.34% | 42.3% | -3.54% | 45.7% | -0.09% |
| EARLY | 134 | 28.8% | -4.43% | 26.5% | -7.84% | 39.4% | -9.13% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1438 | 39.0% | -2.42% | 36.0% | -4.46% | 35.1% | -7.01% |
| 90-94 | 476 | 44.0% | -0.45% | 47.9% | -1.08% | 46.6% | -0.45% |
| <85 | 470 | 41.2% | -0.35% | 51.0% | 0.8% | 55.3% | 1.81% |
| 85-89 | 294 | 48.3% | 0.35% | 54.8% | -0.26% | 55.9% | -0.28% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 237 | 44.0% | 0.7% | 51.7% | 2.24% | 56.8% | 2.41% |
| lifted (0..+5) | 830 | 39.8% | -1.47% | 43.8% | -1.88% | 50.1% | -1.59% |
| extended (>+5) | 1331 | 42.1% | -1.56% | 40.6% | -3.7% | 34.9% | -6.75% |
| pullback (-5..-2) | 164 | 34.4% | -3.21% | 40.5% | -1.95% | 50.9% | 2.32% |
| deep-pb (<-5) | 116 | 48.3% | -0.99% | 45.7% | -3.14% | 44.8% | -1.7% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 994 | 42.1% | -1.46% | 45.3% | -2.03% | 45.4% | -2.89% |
| 30-49% | 1102 | 42.6% | -0.55% | 44.8% | -1.13% | 43.4% | -2.05% |
| 50+% | 582 | 37.6% | -2.94% | 34.7% | -5.81% | 37.6% | -7.62% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 100.0% | 12.2% |
| Energy Minerals | 29 | 79.3% | 8.05% |
| Consumer Durables | 5 | 100.0% | 7.63% |
| Retail Trade | 62 | 70.5% | 5.35% |
| Health Services | 91 | 50.0% | 5.0% |
| Health Technology | 971 | 56.5% | 3.62% |
| Industrial Services | 19 | 31.6% | -0.44% |
| Consumer Non-Durables | 13 | 46.2% | -0.98% |
| Consumer Services | 37 | 40.5% | -2.61% |
| Non-Energy Minerals | 147 | 49.6% | -2.78% |
| Finance | 81 | 40.0% | -4.44% |
| Technology Services | 553 | 42.2% | -5.06% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| SLS | 06-12 | PULLBACK | 98.8 | +48.5% | 7.83 | 13.39 | +71.0% |
| ABSI | 06-10 | EXTENDED | 96.8 | +35.5% | 6.38 | 10.60 | +66.1% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| SLS | 06-13 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |

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
