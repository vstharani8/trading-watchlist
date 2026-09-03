# Momentum Scan Performance Audit — 2026-09-03

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2864. With forward data: 2830.

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
| EXTENDED | 1348 | 42.2% | -1.49% | 39.9% | -3.73% | 35.5% | -6.91% |
| TIGHT | 704 | 41.6% | -0.84% | 46.1% | -0.9% | 49.4% | -0.79% |
| BELOW85 | 349 | 41.9% | -0.39% | 51.6% | 1.01% | 60.5% | 3.62% |
| PULLBACK | 288 | 40.6% | -0.97% | 41.6% | -2.99% | 38.8% | -3.3% |
| EARLY | 141 | 30.7% | -4.19% | 30.0% | -6.74% | 42.9% | -7.45% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1525 | 39.5% | -2.05% | 36.9% | -4.18% | 34.4% | -7.3% |
| 90-94 | 509 | 41.8% | -0.75% | 45.7% | -1.52% | 45.7% | -0.76% |
| <85 | 487 | 42.5% | -0.43% | 49.9% | 0.19% | 55.2% | 1.48% |
| 85-89 | 309 | 47.4% | 0.33% | 53.6% | -0.23% | 59.5% | 0.55% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 257 | 39.1% | -0.32% | 49.8% | 1.3% | 56.1% | 2.66% |
| lifted (0..+5) | 850 | 41.2% | -1.29% | 45.2% | -1.7% | 51.1% | -1.23% |
| extended (>+5) | 1348 | 42.2% | -1.49% | 39.9% | -3.73% | 35.5% | -6.91% |
| pullback (-5..-2) | 202 | 40.4% | -1.98% | 42.0% | -1.93% | 49.2% | 1.07% |
| deep-pb (<-5) | 173 | 38.7% | -0.16% | 39.9% | -3.5% | 29.8% | -6.77% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1027 | 40.6% | -1.52% | 43.9% | -2.27% | 43.2% | -3.5% |
| 30-49% | 1140 | 43.5% | -0.29% | 45.2% | -0.93% | 44.4% | -2.05% |
| 50+% | 663 | 38.5% | -2.62% | 35.8% | -5.69% | 38.9% | -7.16% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 17 | 100.0% | 12.47% |
| Energy Minerals | 29 | 89.7% | 9.75% |
| Consumer Durables | 5 | 100.0% | 7.63% |
| Health Services | 97 | 46.9% | 6.79% |
| Health Technology | 970 | 58.1% | 4.52% |
| Retail Trade | 64 | 65.1% | 4.16% |
| Consumer Non-Durables | 13 | 84.6% | 3.0% |
| Consumer Services | 37 | 43.2% | -2.56% |
| Non-Energy Minerals | 132 | 55.4% | -3.38% |
| Finance | 83 | 42.7% | -3.87% |
| Transportation | 32 | 31.2% | -3.88% |
| Technology Services | 607 | 42.8% | -4.99% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
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
| ALOY | 06-18 | EXTENDED | 92.8 | +95.0% | 17.78 | 8.40 | -52.8% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 255.43 | 124.05 | -51.4% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
