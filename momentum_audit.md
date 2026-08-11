# Momentum Scan Performance Audit — 2026-08-11

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2576. With forward data: 2545.

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
| EXTENDED | 1237 | 40.7% | -2.81% | 39.1% | -3.7% | 34.6% | -7.93% |
| TIGHT | 631 | 38.0% | -1.43% | 45.0% | -0.71% | 47.4% | -1.37% |
| BELOW85 | 280 | 41.2% | -0.23% | 52.3% | 1.92% | 60.6% | 4.88% |
| PULLBACK | 270 | 40.4% | -1.16% | 43.4% | -2.56% | 37.5% | -5.31% |
| EARLY | 127 | 29.9% | -4.56% | 29.9% | -6.05% | 43.3% | -7.21% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1428 | 38.4% | -2.95% | 39.3% | -3.58% | 34.4% | -8.12% |
| 90-94 | 466 | 40.4% | -1.23% | 41.0% | -1.87% | 45.0% | -1.79% |
| <85 | 387 | 41.0% | -0.65% | 49.3% | 1.18% | 56.6% | 3.19% |
| 85-89 | 264 | 42.0% | -0.87% | 48.8% | -1.12% | 52.8% | -0.68% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 226 | 37.9% | -0.23% | 49.6% | 2.14% | 52.7% | 3.26% |
| lifted (0..+5) | 739 | 37.8% | -1.86% | 44.2% | -1.45% | 50.2% | -1.59% |
| extended (>+5) | 1237 | 40.7% | -2.81% | 39.1% | -3.7% | 34.6% | -7.93% |
| pullback (-5..-2) | 183 | 40.3% | -2.17% | 44.8% | -1.04% | 48.6% | 0.23% |
| deep-pb (<-5) | 160 | 39.6% | -0.2% | 40.9% | -3.64% | 28.9% | -9.01% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 883 | 40.2% | -1.94% | 45.2% | -2.05% | 44.4% | -3.68% |
| 30-49% | 970 | 42.9% | -0.65% | 45.4% | -0.31% | 43.2% | -2.53% |
| 50+% | 692 | 34.1% | -4.18% | 33.9% | -5.3% | 36.0% | -8.08% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 9.92% |
| Health Services | 85 | 55.3% | 8.95% |
| Consumer Non-Durables | 2 | 100.0% | 8.38% |
| Consumer Durables | 5 | 80.0% | 6.95% |
| Retail Trade | 59 | 75.4% | 5.81% |
| Health Technology | 839 | 57.7% | 4.5% |
| Energy Minerals | 21 | 55.6% | 0.48% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 42.9% | -3.01% |
| Technology Services | 538 | 43.4% | -4.73% |
| Consumer Services | 30 | 22.2% | -8.19% |
| Miscellaneous | 5 | 20.0% | -11.97% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| SLS | 06-06 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-07 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-08 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |
| SLS | 06-12 | PULLBACK | 98.8 | +48.5% | 7.83 | 13.39 | +71.0% |
| ABSI | 06-09 | EARLY | 96.4 | +30.0% | 6.83 | 11.47 | +67.9% |
| ABSI | 06-10 | EXTENDED | 96.8 | +35.5% | 6.38 | 10.60 | +66.1% |

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
