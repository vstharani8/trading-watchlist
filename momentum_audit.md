# Momentum Scan Performance Audit — 2026-09-09

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2658. With forward data: 2634.

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
| EXTENDED | 1327 | 41.4% | -1.67% | 39.4% | -3.99% | 33.3% | -6.71% |
| TIGHT | 672 | 42.2% | -0.91% | 44.1% | -1.03% | 48.5% | -1.3% |
| BELOW85 | 322 | 38.1% | -0.39% | 50.6% | 1.87% | 58.0% | 4.09% |
| PULLBACK | 181 | 33.1% | -3.36% | 42.0% | -3.72% | 46.4% | 1.17% |
| EARLY | 132 | 25.8% | -4.68% | 24.2% | -7.86% | 35.6% | -8.81% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1406 | 37.7% | -2.66% | 35.7% | -4.73% | 35.8% | -6.72% |
| 90-94 | 468 | 42.0% | -0.71% | 44.8% | -1.4% | 43.3% | -0.85% |
| <85 | 466 | 39.8% | -0.43% | 49.1% | 0.7% | 52.2% | 1.69% |
| 85-89 | 294 | 46.9% | 0.31% | 50.7% | -0.41% | 46.2% | -1.2% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 229 | 41.3% | 0.34% | 50.7% | 2.06% | 55.6% | 2.42% |
| lifted (0..+5) | 834 | 38.5% | -1.57% | 41.4% | -2.1% | 47.3% | -1.85% |
| extended (>+5) | 1327 | 41.4% | -1.67% | 39.4% | -3.99% | 33.3% | -6.71% |
| pullback (-5..-2) | 151 | 30.2% | -3.68% | 39.6% | -2.11% | 49.0% | 2.4% |
| deep-pb (<-5) | 93 | 41.8% | -2.03% | 48.4% | -2.67% | 50.5% | 0.85% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 987 | 41.3% | -1.56% | 44.7% | -2.12% | 45.0% | -2.74% |
| 30-49% | 1084 | 41.1% | -0.7% | 43.0% | -1.38% | 40.6% | -2.18% |
| 50+% | 563 | 35.1% | -3.39% | 32.2% | -6.33% | 35.4% | -7.85% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 29 | 86.2% | 9.37% |
| Consumer Durables | 5 | 100.0% | 7.63% |
| Retail Trade | 60 | 70.0% | 5.49% |
| Health Services | 87 | 37.9% | 3.27% |
| Health Technology | 968 | 54.2% | 2.97% |
| Industrial Services | 18 | 33.3% | 0.36% |
| Non-Energy Minerals | 155 | 52.4% | -1.24% |
| Consumer Services | 37 | 37.8% | -3.6% |
| Finance | 81 | 39.2% | -4.6% |
| Technology Services | 542 | 37.8% | -5.78% |
| Consumer Non-Durables | 13 | 0.0% | -6.07% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| SLS | 06-12 | PULLBACK | 98.8 | +48.5% | 7.83 | 13.39 | +71.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| SLS | 06-13 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-14 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-15 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |

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
