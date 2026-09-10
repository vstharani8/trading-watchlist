# Momentum Scan Performance Audit — 2026-09-10

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2624. With forward data: 2609.

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
| EXTENDED | 1312 | 40.7% | -1.85% | 38.1% | -4.35% | 31.9% | -7.24% |
| TIGHT | 666 | 40.8% | -1.13% | 42.5% | -1.28% | 45.8% | -1.53% |
| BELOW85 | 323 | 38.8% | -0.75% | 49.5% | 1.19% | 55.8% | 3.02% |
| PULLBACK | 177 | 33.1% | -3.81% | 42.3% | -4.68% | 48.0% | 0.87% |
| EARLY | 131 | 25.8% | -4.87% | 24.2% | -8.13% | 35.9% | -9.37% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1392 | 36.6% | -2.89% | 34.2% | -5.09% | 33.7% | -7.03% |
| <85 | 467 | 40.0% | -0.73% | 48.0% | 0.12% | 50.4% | 0.57% |
| 90-94 | 462 | 41.8% | -0.88% | 44.9% | -1.75% | 42.9% | -1.26% |
| 85-89 | 288 | 46.7% | 0.14% | 49.1% | -0.82% | 45.6% | -1.91% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 226 | 38.5% | -0.07% | 47.5% | 1.51% | 51.1% | 1.79% |
| lifted (0..+5) | 831 | 38.5% | -1.71% | 41.1% | -2.3% | 46.2% | -2.17% |
| extended (>+5) | 1312 | 40.7% | -1.85% | 38.1% | -4.35% | 31.9% | -7.24% |
| pullback (-5..-2) | 150 | 29.9% | -4.28% | 38.1% | -3.29% | 48.3% | 1.8% |
| deep-pb (<-5) | 90 | 41.6% | -2.56% | 48.3% | -3.31% | 50.6% | 0.22% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 983 | 40.8% | -1.71% | 43.8% | -2.32% | 44.2% | -3.0% |
| 30-49% | 1075 | 41.1% | -0.93% | 42.4% | -1.81% | 39.8% | -2.73% |
| 50+% | 551 | 32.8% | -3.71% | 29.5% | -6.99% | 31.1% | -8.66% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Energy Minerals | 30 | 86.2% | 9.37% |
| Consumer Durables | 5 | 100.0% | 7.63% |
| Retail Trade | 59 | 69.5% | 5.51% |
| Health Services | 88 | 37.2% | 2.69% |
| Health Technology | 968 | 51.0% | 2.29% |
| Industrial Services | 18 | 33.3% | 0.85% |
| Non-Energy Minerals | 156 | 61.0% | -1.02% |
| Consumer Services | 37 | 32.4% | -4.36% |
| Finance | 81 | 37.5% | -4.72% |
| Technology Services | 534 | 35.3% | -6.41% |
| Transportation | 28 | 21.4% | -6.61% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| SLS | 06-13 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-14 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| SLS | 06-15 | TIGHT | 98.8 | +24.0% | 7.73 | 12.79 | +65.5% |
| PSNL | 06-13 | BELOW85 | 80.5 | +40.6% | 9.79 | 15.79 | +61.3% |

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
