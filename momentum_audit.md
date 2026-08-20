# Momentum Scan Performance Audit — 2026-08-20

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2801. With forward data: 2765.

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
| EXTENDED | 1387 | 40.7% | -2.12% | 39.1% | -3.26% | 35.6% | -6.49% |
| TIGHT | 665 | 39.3% | -1.33% | 45.5% | -0.84% | 48.1% | -1.27% |
| BELOW85 | 304 | 39.7% | -0.61% | 49.8% | 1.24% | 57.9% | 3.71% |
| PULLBACK | 273 | 41.8% | -0.87% | 44.8% | -2.31% | 41.0% | -3.66% |
| EARLY | 136 | 30.1% | -4.48% | 30.8% | -6.35% | 43.6% | -7.62% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1531 | 39.0% | -2.48% | 38.9% | -3.31% | 35.0% | -7.18% |
| 90-94 | 507 | 39.4% | -1.43% | 40.8% | -2.19% | 44.0% | -1.49% |
| <85 | 427 | 41.0% | -0.3% | 48.0% | 0.83% | 55.2% | 2.78% |
| 85-89 | 300 | 43.4% | -0.66% | 51.2% | -1.29% | 55.3% | -0.76% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 234 | 38.2% | -0.47% | 48.7% | 1.48% | 53.9% | 2.75% |
| lifted (0..+5) | 798 | 38.3% | -1.82% | 44.1% | -1.65% | 49.5% | -1.76% |
| extended (>+5) | 1387 | 40.7% | -2.12% | 39.1% | -3.26% | 35.6% | -6.49% |
| pullback (-5..-2) | 187 | 41.5% | -1.96% | 45.4% | -0.89% | 51.4% | 1.4% |
| deep-pb (<-5) | 159 | 40.5% | 0.08% | 42.4% | -3.43% | 31.6% | -7.8% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 988 | 40.9% | -1.61% | 45.5% | -1.79% | 44.8% | -2.99% |
| 30-49% | 1071 | 42.0% | -0.55% | 43.9% | -0.56% | 42.5% | -2.2% |
| 50+% | 706 | 35.1% | -3.8% | 34.1% | -5.46% | 37.1% | -7.8% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 10.5% |
| Energy Minerals | 28 | 88.5% | 10.2% |
| Health Services | 90 | 52.2% | 8.14% |
| Consumer Durables | 5 | 100.0% | 8.0% |
| Retail Trade | 58 | 79.3% | 6.08% |
| Health Technology | 883 | 61.0% | 5.97% |
| Consumer Non-Durables | 9 | 75.0% | 0.46% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 42.9% | -2.66% |
| Consumer Services | 37 | 35.1% | -4.58% |
| Technology Services | 600 | 39.9% | -5.87% |
| Non-Energy Minerals | 65 | 37.9% | -10.47% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-03 | TIGHT | 98.5 | +68.3% | 8.19 | 14.98 | +82.9% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 38.60 | +76.7% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| SLS | 06-06 | TIGHT | 99.2 | +65.9% | 7.98 | 13.76 | +72.4% |

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
