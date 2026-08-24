# Momentum Scan Performance Audit — 2026-08-24

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2868. With forward data: 2837.

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
| EXTENDED | 1426 | 40.8% | -2.14% | 39.5% | -3.34% | 36.0% | -6.43% |
| TIGHT | 678 | 40.5% | -1.22% | 46.6% | -0.73% | 49.2% | -0.93% |
| BELOW85 | 312 | 40.3% | -0.62% | 50.0% | 1.17% | 57.8% | 3.66% |
| PULLBACK | 282 | 41.2% | -0.92% | 44.0% | -2.34% | 40.1% | -3.36% |
| EARLY | 139 | 30.9% | -4.29% | 30.9% | -6.13% | 43.9% | -7.28% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1565 | 39.1% | -2.42% | 39.0% | -3.24% | 35.2% | -6.88% |
| 90-94 | 517 | 40.9% | -1.3% | 43.7% | -1.9% | 46.6% | -1.05% |
| <85 | 446 | 40.0% | -0.63% | 46.7% | 0.11% | 53.3% | 2.07% |
| 85-89 | 309 | 44.7% | -0.6% | 51.3% | -1.22% | 55.9% | -0.65% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 237 | 39.0% | -0.41% | 49.6% | 1.5% | 54.7% | 3.01% |
| lifted (0..+5) | 817 | 39.4% | -1.72% | 44.9% | -1.54% | 50.2% | -1.52% |
| extended (>+5) | 1426 | 40.8% | -2.14% | 39.5% | -3.34% | 36.0% | -6.43% |
| pullback (-5..-2) | 189 | 41.2% | -1.95% | 44.9% | -0.91% | 50.3% | 1.36% |
| deep-pb (<-5) | 168 | 39.9% | -0.02% | 41.7% | -3.45% | 31.3% | -7.2% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1008 | 41.7% | -1.51% | 46.3% | -1.66% | 45.5% | -2.6% |
| 30-49% | 1106 | 42.5% | -0.56% | 44.7% | -0.62% | 43.4% | -2.1% |
| 50+% | 723 | 34.5% | -3.85% | 33.3% | -5.58% | 36.2% | -7.83% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 13.12% |
| Energy Minerals | 30 | 82.8% | 9.58% |
| Health Services | 93 | 52.7% | 8.17% |
| Consumer Durables | 5 | 80.0% | 7.44% |
| Health Technology | 906 | 60.9% | 6.17% |
| Retail Trade | 58 | 74.1% | 5.77% |
| Consumer Non-Durables | 11 | 80.0% | 1.74% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 84 | 42.9% | -2.65% |
| Consumer Services | 37 | 40.5% | -3.76% |
| Technology Services | 615 | 41.7% | -5.47% |
| Non-Energy Minerals | 77 | 49.3% | -6.58% |

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
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 38.66 | +76.9% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |

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
