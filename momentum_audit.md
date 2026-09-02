# Momentum Scan Performance Audit — 2026-09-02

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 2920. With forward data: 2890.

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
| EXTENDED | 1398 | 42.4% | -1.38% | 39.6% | -3.42% | 33.8% | -6.81% |
| TIGHT | 714 | 40.8% | -0.83% | 45.2% | -0.78% | 46.9% | -1.25% |
| BELOW85 | 348 | 38.3% | -0.65% | 46.9% | 0.62% | 52.5% | 2.74% |
| PULLBACK | 286 | 40.8% | -0.93% | 42.3% | -2.8% | 39.1% | -3.38% |
| EARLY | 144 | 31.9% | -4.04% | 31.2% | -6.29% | 43.8% | -7.3% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 1563 | 39.8% | -1.96% | 37.3% | -3.82% | 33.2% | -7.54% |
| 90-94 | 522 | 41.2% | -0.74% | 44.5% | -1.42% | 44.3% | -0.9% |
| <85 | 490 | 39.4% | -0.54% | 45.1% | -0.11% | 48.4% | 1.52% |
| 85-89 | 315 | 47.3% | 0.35% | 53.4% | -0.26% | 55.9% | -0.0% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 257 | 37.8% | -0.16% | 47.8% | 1.45% | 51.8% | 2.41% |
| lifted (0..+5) | 868 | 39.3% | -1.42% | 43.1% | -1.74% | 47.2% | -1.85% |
| extended (>+5) | 1398 | 42.4% | -1.38% | 39.6% | -3.42% | 33.8% | -6.81% |
| pullback (-5..-2) | 197 | 41.2% | -1.83% | 43.3% | -1.47% | 49.5% | 1.21% |
| deep-pb (<-5) | 170 | 39.6% | -0.25% | 40.8% | -3.71% | 30.8% | -7.17% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 1039 | 40.4% | -1.44% | 43.0% | -2.23% | 39.8% | -3.88% |
| 30-49% | 1152 | 42.2% | -0.44% | 43.2% | -1.08% | 41.0% | -2.48% |
| 50+% | 699 | 39.1% | -2.31% | 37.2% | -4.73% | 39.7% | -6.67% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 18 | 100.0% | 13.19% |
| Energy Minerals | 30 | 83.3% | 8.59% |
| Health Services | 98 | 51.5% | 7.24% |
| Consumer Durables | 5 | 80.0% | 6.57% |
| Consumer Non-Durables | 13 | 100.0% | 4.78% |
| Health Technology | 967 | 56.0% | 4.53% |
| Retail Trade | 64 | 66.7% | 4.35% |
| Transportation | 33 | 33.3% | -3.04% |
| Consumer Services | 37 | 40.5% | -3.4% |
| Finance | 83 | 41.5% | -3.57% |
| Technology Services | 627 | 42.5% | -4.94% |
| Industrial Services | 24 | 25.0% | -8.08% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| SLS | 06-10 | PULLBACK | 99.0 | +55.2% | 7.15 | 12.76 | +78.5% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| ABSI | 06-05 | EXTENDED | 96.7 | +30.5% | 6.40 | 11.33 | +77.0% |
| SLS | 06-09 | PULLBACK | 98.9 | +61.2% | 7.68 | 13.51 | +75.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| NLST | 08-06 | EXTENDED | 0.0 | +31.2% | 3.82 | 6.65 | +74.1% |
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
| ALOY | 06-18 | EXTENDED | 92.8 | +95.0% | 17.78 | 8.40 | -52.8% |
| HQ | 06-24 | EXTENDED | 97.5 | +174.4% | 28.41 | 13.74 | -51.6% |
| GLW | 06-30 | EXTENDED | 98.0 | +38.9% | 255.43 | 124.05 | -51.4% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
