# Momentum Scan Performance Audit — 2026-08-12

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2518. With forward data: 2487.

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
| EXTENDED | 1200 | 41.3% | -2.58% | 38.9% | -3.86% | 34.5% | -7.84% |
| TIGHT | 618 | 38.1% | -1.45% | 44.7% | -0.95% | 46.8% | -1.58% |
| BELOW85 | 276 | 40.7% | -0.45% | 51.6% | 1.54% | 60.0% | 4.22% |
| PULLBACK | 267 | 41.4% | -1.0% | 44.0% | -2.48% | 37.6% | -4.97% |
| EARLY | 126 | 28.8% | -4.68% | 29.6% | -6.57% | 43.2% | -7.79% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1394 | 38.7% | -2.78% | 39.1% | -3.51% | 33.7% | -8.05% |
| 90-94 | 456 | 40.5% | -1.29% | 40.8% | -2.38% | 45.4% | -1.92% |
| <85 | 375 | 41.8% | -0.7% | 49.6% | 0.46% | 57.1% | 2.54% |
| 85-89 | 262 | 41.4% | -0.87% | 47.3% | -1.66% | 51.6% | -1.06% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 218 | 37.2% | -0.48% | 48.2% | 1.53% | 50.9% | 2.65% |
| lifted (0..+5) | 729 | 37.7% | -1.91% | 44.1% | -1.7% | 50.0% | -1.89% |
| extended (>+5) | 1200 | 41.3% | -2.58% | 38.9% | -3.86% | 34.5% | -7.84% |
| pullback (-5..-2) | 182 | 41.2% | -2.1% | 45.1% | -1.01% | 48.4% | 0.34% |
| deep-pb (<-5) | 158 | 40.1% | 0.03% | 41.4% | -3.56% | 29.3% | -8.79% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 882 | 41.2% | -1.77% | 45.8% | -2.06% | 45.2% | -3.57% |
| 30-49% | 954 | 43.2% | -0.6% | 44.8% | -0.58% | 42.7% | -2.69% |
| 50+% | 651 | 32.9% | -4.31% | 32.3% | -5.89% | 34.0% | -8.74% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Services | 86 | 55.3% | 8.54% |
| Commercial Services | 19 | 84.2% | 7.3% |
| Consumer Durables | 5 | 80.0% | 6.48% |
| Retail Trade | 58 | 74.1% | 5.85% |
| Energy Minerals | 22 | 81.0% | 4.38% |
| Health Technology | 835 | 56.0% | 4.26% |
| Process Industries | 2 | 0.0% | -0.66% |
| Consumer Non-Durables | 2 | 0.0% | -0.83% |
| Transportation | 35 | 37.1% | -0.97% |
| Finance | 83 | 43.4% | -2.78% |
| Technology Services | 524 | 43.0% | -5.22% |
| Consumer Services | 31 | 20.0% | -7.61% |

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
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 9.76 | +68.3% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 9.76 | +68.3% |

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
