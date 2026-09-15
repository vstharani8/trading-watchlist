# Momentum Scan Performance Audit — 2026-09-15

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2375. With forward data: 2372.

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
| EXTENDED | 1205 | 39.1% | -2.26% | 35.4% | -5.59% | 30.7% | -7.69% |
| TIGHT | 601 | 39.8% | -1.5% | 38.1% | -2.86% | 44.1% | -1.47% |
| BELOW85 | 277 | 39.9% | -0.57% | 38.8% | -1.15% | 43.1% | 0.48% |
| PULLBACK | 168 | 31.0% | -3.77% | 39.9% | -5.49% | 48.8% | 1.31% |
| EARLY | 121 | 25.6% | -5.22% | 25.6% | -7.96% | 35.5% | -8.66% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1263 | 35.1% | -3.29% | 31.1% | -6.58% | 33.8% | -7.19% |
| <85 | 421 | 40.5% | -0.71% | 40.5% | -1.62% | 38.8% | -1.77% |
| 90-94 | 419 | 40.2% | -1.55% | 40.4% | -3.33% | 40.9% | -1.53% |
| 85-89 | 269 | 45.4% | 0.18% | 48.0% | -1.04% | 43.9% | -1.45% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 201 | 41.2% | -0.42% | 39.2% | -2.12% | 45.7% | -0.49% |
| lifted (0..+5) | 755 | 36.5% | -2.08% | 36.0% | -3.45% | 41.7% | -2.37% |
| extended (>+5) | 1205 | 39.1% | -2.26% | 35.4% | -5.59% | 30.7% | -7.69% |
| pullback (-5..-2) | 132 | 31.8% | -4.01% | 37.1% | -4.94% | 47.7% | 0.42% |
| deep-pb (<-5) | 79 | 40.5% | -1.7% | 44.3% | -3.11% | 50.6% | 3.17% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 909 | 39.3% | -1.93% | 41.2% | -3.16% | 40.4% | -3.49% |
| 30-49% | 969 | 39.3% | -1.54% | 35.8% | -4.0% | 36.1% | -3.85% |
| 50+% | 494 | 33.6% | -3.67% | 28.3% | -7.94% | 33.0% | -8.02% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Consumer Durables | 2 | 100.0% | 9.0% |
| Energy Minerals | 30 | 73.3% | 8.24% |
| Retail Trade | 54 | 59.3% | 4.66% |
| Health Technology | 935 | 50.1% | 1.19% |
| Industrial Services | 18 | 33.3% | -0.38% |
| Health Services | 78 | 29.5% | -0.97% |
| Consumer Services | 38 | 31.6% | -4.26% |
| Finance | 77 | 40.3% | -4.66% |
| Technology Services | 466 | 41.1% | -4.82% |
| Consumer Non-Durables | 13 | 0.0% | -5.43% |
| Transportation | 23 | 21.7% | -7.74% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |
| PSNL | 07-24 | PULLBACK | 94.3 | +23.7% | 11.78 | 18.38 | +56.0% |
| IOVA | 07-22 | EXTENDED | 96.1 | +38.0% | 5.17 | 7.99 | +54.5% |
| ABCL | 07-15 | PULLBACK | 92.6 | +27.2% | 6.74 | 10.35 | +53.6% |

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
