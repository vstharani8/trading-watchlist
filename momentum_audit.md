# Momentum Scan Performance Audit — 2026-09-25

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2100. With forward data: 2077.

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
| EXTENDED | 1047 | 38.6% | -2.59% | 39.2% | -4.68% | 39.4% | -4.69% |
| TIGHT | 524 | 40.1% | -1.72% | 41.7% | -1.97% | 55.3% | 1.99% |
| BELOW85 | 253 | 35.1% | -2.07% | 40.6% | -1.84% | 45.8% | 0.67% |
| PULLBACK | 147 | 28.6% | -4.59% | 39.5% | -5.68% | 56.5% | 5.84% |
| EARLY | 106 | 26.7% | -5.27% | 23.8% | -7.48% | 42.9% | -6.2% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1077 | 37.2% | -3.06% | 36.2% | -5.05% | 44.5% | -2.62% |
| <85 | 399 | 35.2% | -2.03% | 42.1% | -2.09% | 43.4% | -1.07% |
| 90-94 | 353 | 36.5% | -2.71% | 40.2% | -3.47% | 49.9% | 1.16% |
| 85-89 | 248 | 41.5% | -1.26% | 46.4% | -2.1% | 47.6% | -2.57% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 178 | 39.5% | -0.98% | 42.4% | -2.1% | 53.1% | 1.32% |
| lifted (0..+5) | 666 | 35.7% | -2.66% | 37.4% | -3.11% | 49.5% | 0.0% |
| extended (>+5) | 1047 | 38.6% | -2.59% | 39.2% | -4.68% | 39.4% | -4.69% |
| pullback (-5..-2) | 115 | 30.4% | -3.98% | 38.3% | -4.49% | 55.7% | 4.54% |
| deep-pb (<-5) | 71 | 36.6% | -3.54% | 50.7% | -2.34% | 64.8% | 9.24% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 830 | 39.4% | -2.11% | 44.4% | -2.61% | 48.2% | -1.04% |
| 30-49% | 842 | 37.0% | -2.42% | 37.4% | -3.82% | 42.8% | -2.04% |
| 50+% | 405 | 33.3% | -3.88% | 32.6% | -6.44% | 46.2% | -2.15% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 32 | 75.0% | 7.06% |
| Retail Trade | 50 | 50.0% | 3.6% |
| Health Technology | 841 | 57.6% | 3.33% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Industrial Services | 20 | 36.8% | -0.34% |
| Technology Services | 414 | 49.0% | -1.57% |
| Finance | 72 | 50.7% | -2.4% |
| Transportation | 15 | 33.3% | -2.44% |
| Health Services | 58 | 22.4% | -2.51% |
| Consumer Services | 36 | 33.3% | -3.57% |
| Producer Manufacturing | 48 | 33.3% | -9.02% |

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
| SNDK | 06-30 | TIGHT | 100.0 | +21.9% | 2273.73 | 1015.89 | -55.3% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 254.95 | 123.82 | -51.4% |
| OUST | 06-30 | EXTENDED | 96.8 | +21.0% | 62.52 | 31.30 | -49.9% |
| FCEL | 06-30 | EXTENDED | 99.4 | +23.9% | 36.01 | 18.08 | -49.8% |
| ACMR | 06-30 | EXTENDED | 98.5 | +28.1% | 126.89 | 65.30 | -48.5% |
| ALAB | 06-30 | EXTENDED | 99.1 | +31.0% | 483.02 | 249.74 | -48.3% |
| SNDK | 06-28 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| SNDK | 06-29 | TIGHT | 100.0 | +27.0% | 2050.39 | 1096.10 | -46.5% |
| MRVL | 06-30 | TIGHT | 98.0 | +35.9% | 297.82 | 163.40 | -45.1% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
