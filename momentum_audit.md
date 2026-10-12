# Momentum Scan Performance Audit — 2026-10-12

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1536. With forward data: 1536.

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
| EXTENDED | 817 | 41.9% | -1.03% | 45.2% | -1.48% | 42.4% | -0.96% |
| TIGHT | 377 | 45.4% | -0.22% | 48.5% | 0.66% | 54.1% | 3.97% |
| BELOW85 | 198 | 38.9% | -1.34% | 46.0% | -0.65% | 37.9% | -1.4% |
| PULLBACK | 87 | 33.3% | -3.15% | 49.4% | -2.39% | 69.0% | 11.6% |
| EARLY | 57 | 40.4% | -1.47% | 35.1% | -2.37% | 50.9% | -0.81% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 794 | 43.6% | -0.6% | 43.8% | -0.95% | 49.1% | 2.72% |
| <85 | 329 | 37.7% | -1.57% | 45.9% | -1.27% | 38.3% | -2.32% |
| 90-94 | 241 | 41.5% | -1.79% | 51.9% | -0.15% | 56.0% | 2.79% |
| 85-89 | 172 | 41.9% | -0.69% | 48.3% | -1.26% | 37.2% | -3.73% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 121 | 43.0% | 0.04% | 45.5% | -0.31% | 52.1% | 1.72% |
| lifted (0..+5) | 476 | 43.1% | -0.76% | 45.8% | -0.21% | 47.5% | 1.37% |
| extended (>+5) | 817 | 41.9% | -1.03% | 45.2% | -1.48% | 42.4% | -0.96% |
| pullback (-5..-2) | 71 | 35.2% | -2.85% | 49.3% | -0.39% | 62.0% | 9.89% |
| deep-pb (<-5) | 51 | 35.3% | -2.87% | 56.9% | -1.13% | 68.6% | 12.1% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 657 | 41.9% | -0.7% | 49.0% | -0.11% | 49.5% | 1.55% |
| 30-49% | 600 | 41.7% | -1.17% | 42.5% | -1.43% | 40.7% | -0.97% |
| 50+% | 279 | 42.1% | -1.39% | 46.5% | -1.81% | 52.4% | 3.59% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 482 | 65.8% | 10.45% |
| Energy Minerals | 32 | 78.1% | 7.67% |
| Producer Manufacturing | 16 | 56.2% | 2.99% |
| Industrial Services | 28 | 53.6% | 2.11% |
| Health Services | 30 | 33.3% | 0.61% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Technology Services | 381 | 49.3% | 0.18% |
| Consumer Services | 21 | 33.3% | -1.29% |
| Finance | 34 | 32.4% | -5.3% |
| Electronic Technology | 317 | 30.3% | -6.29% |
| Retail Trade | 13 | 0.0% | -6.44% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| ABCL | 07-18 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-19 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| ABCL | 07-20 | PULLBACK | 91.3 | +24.2% | 5.80 | 11.20 | +93.1% |
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| ABCL | 07-16 | PULLBACK | 91.8 | +22.8% | 6.16 | 10.97 | +78.1% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.62 | +70.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 17.09 | -55.8% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEVA | 08-12 | EXTENDED | 91.2 | +23.6% | 25.16 | 14.97 | -40.5% |
| AXTI | 08-15 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| AXTI | 08-17 | EXTENDED | 100.0 | +46.4% | 95.97 | 57.70 | -39.9% |
| ALOY | 08-15 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| ALOY | 08-17 | EXTENDED | 93.6 | +37.4% | 13.85 | 8.47 | -38.9% |
| AAOI | 08-15 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |
| AAOI | 08-17 | EXTENDED | 99.4 | +21.4% | 154.89 | 95.29 | -38.5% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
