# Momentum Scan Performance Audit — 2026-08-21

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2837. With forward data: 2801.

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
| EXTENDED | 1406 | 40.2% | -2.26% | 37.9% | -3.54% | 34.0% | -6.75% |
| TIGHT | 671 | 38.9% | -1.34% | 45.0% | -0.89% | 47.4% | -1.37% |
| BELOW85 | 308 | 38.2% | -0.82% | 48.0% | 0.95% | 55.9% | 3.41% |
| PULLBACK | 277 | 41.4% | -0.89% | 44.3% | -2.4% | 40.3% | -3.82% |
| EARLY | 139 | 30.1% | -4.45% | 30.1% | -6.34% | 42.6% | -7.64% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1547 | 38.7% | -2.5% | 38.1% | -3.34% | 34.0% | -7.22% |
| 90-94 | 513 | 39.1% | -1.54% | 39.8% | -2.33% | 42.8% | -1.56% |
| <85 | 437 | 39.1% | -0.73% | 45.9% | 0.03% | 52.9% | 1.97% |
| 85-89 | 304 | 42.7% | -0.72% | 50.0% | -1.5% | 54.0% | -1.04% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 236 | 37.6% | -0.57% | 47.9% | 1.31% | 53.0% | 2.57% |
| lifted (0..+5) | 809 | 37.6% | -1.88% | 43.1% | -1.74% | 48.2% | -1.9% |
| extended (>+5) | 1406 | 40.2% | -2.26% | 37.9% | -3.54% | 34.0% | -6.75% |
| pullback (-5..-2) | 187 | 41.2% | -1.96% | 44.9% | -0.98% | 50.3% | 1.12% |
| deep-pb (<-5) | 163 | 40.3% | 0.05% | 42.1% | -3.51% | 31.4% | -7.87% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 997 | 40.5% | -1.67% | 44.4% | -1.95% | 43.3% | -3.13% |
| 30-49% | 1089 | 41.5% | -0.69% | 43.0% | -0.82% | 41.5% | -2.45% |
| 50+% | 715 | 34.3% | -3.89% | 33.0% | -5.56% | 35.8% | -7.92% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 11.38% |
| Health Services | 91 | 52.2% | 8.27% |
| Consumer Durables | 5 | 100.0% | 7.71% |
| Health Technology | 895 | 60.4% | 6.2% |
| Retail Trade | 58 | 77.6% | 5.86% |
| Energy Minerals | 29 | 71.4% | 5.73% |
| Consumer Non-Durables | 10 | 55.6% | -0.14% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 42.9% | -2.65% |
| Consumer Services | 37 | 32.4% | -5.56% |
| Technology Services | 607 | 37.8% | -6.29% |
| Non-Energy Minerals | 71 | 46.2% | -9.22% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 39.66 | +81.5% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.99 | +80.2% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| AMLX | 08-13 | EXTENDED | 96.2 | +33.4% | 22.48 | 39.66 | +76.4% |

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
