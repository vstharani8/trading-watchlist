# Momentum Scan Performance Audit — 2026-09-14

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2424. With forward data: 2419.

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
| EXTENDED | 1226 | 39.0% | -2.13% | 34.8% | -5.7% | 29.9% | -7.87% |
| TIGHT | 618 | 39.8% | -1.5% | 38.9% | -2.84% | 43.9% | -1.94% |
| BELOW85 | 281 | 39.3% | -0.48% | 39.6% | -0.9% | 44.3% | 0.86% |
| PULLBACK | 170 | 31.0% | -3.83% | 39.3% | -5.55% | 47.6% | 1.38% |
| EARLY | 124 | 28.2% | -4.51% | 26.6% | -7.37% | 37.1% | -8.61% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1294 | 35.2% | -3.16% | 30.8% | -6.65% | 33.7% | -7.41% |
| 90-94 | 430 | 40.3% | -1.36% | 41.0% | -3.06% | 39.4% | -1.7% |
| <85 | 425 | 40.3% | -0.59% | 40.8% | -1.47% | 39.9% | -1.37% |
| 85-89 | 270 | 45.2% | 0.11% | 47.4% | -1.16% | 42.2% | -2.09% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 205 | 40.9% | -0.42% | 40.9% | -1.69% | 46.8% | 0.05% |
| lifted (0..+5) | 774 | 37.0% | -1.92% | 36.7% | -3.34% | 42.0% | -2.73% |
| extended (>+5) | 1226 | 39.0% | -2.13% | 34.8% | -5.7% | 29.9% | -7.87% |
| pullback (-5..-2) | 135 | 30.6% | -4.3% | 35.1% | -5.36% | 44.8% | -0.17% |
| deep-pb (<-5) | 79 | 41.0% | -1.55% | 46.2% | -2.64% | 52.6% | 4.25% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 924 | 39.6% | -1.85% | 40.8% | -3.32% | 39.9% | -3.68% |
| 30-49% | 987 | 39.4% | -1.36% | 36.5% | -3.8% | 36.5% | -3.74% |
| 50+% | 508 | 33.1% | -3.62% | 27.5% | -7.94% | 31.5% | -8.58% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 30 | 90.0% | 10.0% |
| Consumer Durables | 2 | 100.0% | 9.0% |
| Retail Trade | 55 | 61.8% | 4.81% |
| Health Technology | 940 | 49.0% | 0.86% |
| Industrial Services | 18 | 33.3% | -0.01% |
| Health Services | 80 | 31.2% | -0.4% |
| Consumer Services | 38 | 34.2% | -4.34% |
| Finance | 78 | 38.5% | -4.81% |
| Technology Services | 481 | 35.3% | -6.49% |
| Non-Energy Minerals | 154 | 20.3% | -6.96% |
| Transportation | 24 | 20.8% | -7.67% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| PSNL | 06-17 | BELOW85 | 81.2 | +48.6% | 9.75 | 15.39 | +57.9% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |
| PSNL | 07-24 | PULLBACK | 94.3 | +23.7% | 11.78 | 18.38 | +56.0% |
| IOVA | 07-22 | EXTENDED | 96.1 | +38.0% | 5.17 | 7.99 | +54.5% |

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
