# Momentum Scan Performance Audit — 2026-09-18

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2259. With forward data: 2248.

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
| EXTENDED | 1135 | 39.3% | -2.21% | 36.9% | -5.07% | 34.7% | -6.21% |
| TIGHT | 575 | 40.8% | -1.43% | 42.3% | -2.19% | 50.9% | 0.12% |
| BELOW85 | 265 | 38.9% | -0.95% | 41.5% | -0.88% | 47.9% | 1.41% |
| PULLBACK | 159 | 28.5% | -4.69% | 38.0% | -6.13% | 50.6% | 2.73% |
| EARLY | 114 | 27.4% | -5.06% | 26.5% | -7.24% | 41.6% | -7.0% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1190 | 36.1% | -3.14% | 33.8% | -5.76% | 38.9% | -5.31% |
| <85 | 405 | 39.0% | -1.14% | 42.2% | -1.56% | 43.7% | -0.87% |
| 90-94 | 391 | 39.5% | -1.71% | 41.5% | -3.12% | 46.2% | 0.11% |
| 85-89 | 262 | 45.4% | -0.13% | 48.9% | -1.25% | 46.6% | -1.27% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 194 | 41.2% | -0.66% | 43.3% | -1.91% | 51.5% | 0.27% |
| lifted (0..+5) | 719 | 37.2% | -2.1% | 38.8% | -2.86% | 47.4% | -0.85% |
| extended (>+5) | 1135 | 39.3% | -2.21% | 36.9% | -5.07% | 34.7% | -6.21% |
| pullback (-5..-2) | 125 | 30.6% | -3.99% | 37.9% | -4.77% | 50.0% | 2.04% |
| deep-pb (<-5) | 75 | 37.3% | -3.42% | 45.3% | -3.47% | 58.7% | 5.2% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 876 | 40.0% | -1.86% | 43.6% | -2.7% | 45.1% | -2.28% |
| 30-49% | 918 | 39.3% | -1.7% | 37.3% | -3.68% | 39.5% | -2.63% |
| 50+% | 454 | 32.8% | -3.77% | 30.6% | -7.24% | 40.6% | -5.61% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 80.6% | 8.49% |
| Retail Trade | 52 | 53.8% | 4.17% |
| Health Technology | 915 | 54.1% | 2.18% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 18 | 33.3% | -0.58% |
| Health Services | 73 | 26.0% | -1.94% |
| Technology Services | 433 | 46.5% | -3.44% |
| Consumer Services | 38 | 34.2% | -3.67% |
| Finance | 74 | 40.5% | -4.74% |
| Transportation | 20 | 25.0% | -7.38% |
| Non-Energy Minerals | 150 | 20.0% | -7.51% |

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
| HQ | 06-23 | EXTENDED | 98.0 | +215.4% | 33.39 | 14.64 | -56.1% |
| SNDK | 06-30 | TIGHT | 100.0 | +21.9% | 2273.73 | 1015.89 | -55.3% |
| ALOY | 06-24 | EXTENDED | 96.2 | +98.7% | 16.67 | 7.47 | -55.2% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |
| ALOY | 06-25 | TIGHT | 95.2 | +72.7% | 14.25 | 7.03 | -50.7% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |
| FCEL | 06-30 | EXTENDED | 99.4 | +23.9% | 36.01 | 18.08 | -49.8% |
| ACMR | 06-30 | EXTENDED | 98.5 | +28.1% | 126.89 | 65.30 | -48.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
