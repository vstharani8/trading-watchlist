# Momentum Scan Performance Audit — 2026-09-11

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2581. With forward data: 2557.

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
| EXTENDED | 1287 | 40.1% | -1.93% | 36.6% | -4.74% | 29.4% | -7.97% |
| TIGHT | 657 | 39.1% | -1.45% | 39.3% | -2.1% | 42.2% | -2.28% |
| BELOW85 | 308 | 37.8% | -0.71% | 45.1% | 0.51% | 48.4% | 2.22% |
| PULLBACK | 176 | 30.5% | -3.97% | 39.7% | -4.99% | 45.4% | 0.73% |
| EARLY | 129 | 26.4% | -4.79% | 24.0% | -8.07% | 34.9% | -9.53% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1375 | 35.7% | -3.04% | 32.2% | -5.67% | 31.8% | -7.73% |
| 90-94 | 457 | 40.7% | -1.09% | 41.9% | -2.34% | 38.1% | -1.98% |
| <85 | 442 | 39.3% | -0.65% | 45.2% | -0.16% | 44.3% | 0.05% |
| 85-89 | 283 | 44.9% | -0.06% | 47.7% | -1.13% | 42.8% | -2.49% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 220 | 39.0% | -0.39% | 45.0% | 0.23% | 47.7% | 0.67% |
| lifted (0..+5) | 821 | 36.5% | -1.94% | 37.2% | -2.9% | 41.0% | -2.91% |
| extended (>+5) | 1287 | 40.1% | -1.93% | 36.6% | -4.74% | 29.4% | -7.97% |
| pullback (-5..-2) | 146 | 29.2% | -4.39% | 37.5% | -3.8% | 46.5% | 1.09% |
| deep-pb (<-5) | 83 | 39.8% | -2.15% | 45.8% | -3.21% | 49.4% | 1.82% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 973 | 39.5% | -1.84% | 41.8% | -2.75% | 40.2% | -3.67% |
| 30-49% | 1045 | 39.9% | -1.1% | 39.5% | -2.47% | 36.6% | -3.43% |
| 50+% | 539 | 32.7% | -3.78% | 27.7% | -7.42% | 28.8% | -9.35% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 30 | 86.7% | 9.45% |
| Consumer Durables | 4 | 100.0% | 7.86% |
| Retail Trade | 58 | 60.3% | 4.61% |
| Health Services | 86 | 36.0% | 1.82% |
| Health Technology | 965 | 48.8% | 1.35% |
| Industrial Services | 18 | 33.3% | 0.16% |
| Finance | 81 | 37.5% | -4.84% |
| Non-Energy Minerals | 156 | 26.5% | -5.26% |
| Consumer Services | 37 | 22.2% | -5.48% |
| Technology Services | 523 | 35.4% | -6.56% |
| Transportation | 27 | 22.2% | -6.84% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| SLS | 06-14 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-15 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| PSNL | 06-14 | BELOW85 | 80.4 | +40.6% | 9.79 | 15.79 | +61.3% |
| PSNL | 06-15 | BELOW85 | 80.4 | +40.6% | 9.79 | 15.79 | +61.3% |

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
