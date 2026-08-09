# Momentum Scan Performance Audit — 2026-08-09

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2664. With forward data: 2598.

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
| EXTENDED | 1243 | 39.7% | -3.11% | 40.3% | -2.93% | 34.8% | -7.75% |
| TIGHT | 663 | 37.4% | -1.69% | 45.6% | -0.55% | 46.6% | -1.5% |
| BELOW85 | 286 | 41.3% | -0.32% | 51.4% | 1.83% | 59.1% | 4.31% |
| PULLBACK | 273 | 39.6% | -1.54% | 43.2% | -2.59% | 38.1% | -6.63% |
| EARLY | 133 | 30.8% | -4.51% | 31.6% | -5.58% | 44.4% | -6.75% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1457 | 37.2% | -3.39% | 39.9% | -3.41% | 34.0% | -8.34% |
| 90-94 | 475 | 40.0% | -1.28% | 41.9% | -1.12% | 45.1% | -2.19% |
| <85 | 394 | 40.9% | -0.85% | 48.5% | 1.15% | 54.8% | 2.48% |
| 85-89 | 272 | 42.3% | -0.84% | 51.1% | 0.42% | 54.0% | 0.41% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 228 | 38.2% | -0.21% | 49.6% | 2.05% | 53.5% | 3.4% |
| lifted (0..+5) | 780 | 37.4% | -2.11% | 44.6% | -1.23% | 48.8% | -1.84% |
| extended (>+5) | 1243 | 39.7% | -3.11% | 40.3% | -2.93% | 34.8% | -7.75% |
| pullback (-5..-2) | 187 | 39.0% | -2.54% | 44.4% | -1.14% | 48.1% | -1.06% |
| deep-pb (<-5) | 160 | 39.4% | -0.42% | 40.6% | -3.67% | 30.0% | -10.06% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 862 | 39.2% | -2.27% | 44.8% | -2.12% | 42.8% | -4.47% |
| 30-49% | 990 | 41.8% | -0.97% | 45.9% | -0.02% | 43.0% | -2.86% |
| 50+% | 746 | 34.3% | -4.27% | 36.2% | -4.14% | 37.3% | -7.26% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 100.0% | 10.04% |
| Health Services | 85 | 55.3% | 8.58% |
| Consumer Non-Durables | 1 | 100.0% | 8.38% |
| Consumer Durables | 5 | 80.0% | 7.2% |
| Retail Trade | 59 | 72.9% | 5.59% |
| Health Technology | 830 | 57.7% | 3.62% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 86 | 43.0% | -2.54% |
| Technology Services | 560 | 42.9% | -4.65% |
| Energy Minerals | 19 | 26.3% | -4.81% |
| Consumer Services | 27 | 25.9% | -6.1% |
| Miscellaneous | 7 | 28.6% | -7.72% |

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
