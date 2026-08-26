# Momentum Scan Performance Audit — 2026-08-26

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2925. With forward data: 2896.

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
| EXTENDED | 1455 | 41.6% | -2.17% | 40.1% | -3.56% | 36.3% | -6.57% |
| TIGHT | 689 | 39.1% | -1.25% | 45.3% | -0.73% | 47.8% | -1.15% |
| BELOW85 | 323 | 40.1% | -0.72% | 48.9% | 1.04% | 55.5% | 3.38% |
| PULLBACK | 285 | 40.6% | -1.09% | 43.5% | -2.49% | 39.9% | -3.68% |
| EARLY | 144 | 32.2% | -4.18% | 32.2% | -6.01% | 44.1% | -7.23% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1590 | 39.2% | -2.49% | 38.8% | -3.45% | 34.7% | -7.14% |
| 90-94 | 526 | 40.6% | -1.32% | 42.9% | -1.93% | 45.8% | -1.1% |
| <85 | 463 | 41.2% | -0.75% | 47.1% | -0.1% | 52.9% | 1.69% |
| 85-89 | 317 | 43.9% | -0.51% | 51.0% | -1.16% | 56.1% | -0.62% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 242 | 38.3% | -0.34% | 49.2% | 1.62% | 54.2% | 2.91% |
| lifted (0..+5) | 838 | 38.6% | -1.79% | 43.7% | -1.6% | 48.4% | -1.75% |
| extended (>+5) | 1455 | 41.6% | -2.17% | 40.1% | -3.56% | 36.3% | -6.57% |
| pullback (-5..-2) | 191 | 41.4% | -2.01% | 45.0% | -1.05% | 50.8% | 1.13% |
| deep-pb (<-5) | 170 | 38.7% | -0.31% | 40.5% | -3.59% | 30.4% | -7.47% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1025 | 41.4% | -1.54% | 45.1% | -1.94% | 44.1% | -3.01% |
| 30-49% | 1132 | 42.6% | -0.71% | 44.6% | -0.86% | 43.1% | -2.34% |
| 50+% | 739 | 35.3% | -3.77% | 34.6% | -5.39% | 37.1% | -7.65% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 19 | 100.0% | 14.37% |
| Health Services | 95 | 53.2% | 7.91% |
| Consumer Durables | 5 | 80.0% | 6.76% |
| Health Technology | 924 | 61.4% | 6.19% |
| Retail Trade | 60 | 77.6% | 5.92% |
| Consumer Non-Durables | 12 | 66.7% | 1.16% |
| Energy Minerals | 30 | 53.3% | 0.4% |
| Transportation | 35 | 37.1% | -0.97% |
| Consumer Services | 37 | 45.9% | -2.02% |
| Finance | 84 | 44.0% | -2.63% |
| Non-Energy Minerals | 91 | 63.9% | -3.45% |
| Technology Services | 632 | 39.4% | -5.88% |

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
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
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
