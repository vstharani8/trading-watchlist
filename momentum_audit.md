# Momentum Scan Performance Audit — 2026-10-30

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1268. With forward data: 1268.

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
| EXTENDED | 737 | 41.2% | -1.31% | 41.6% | -3.66% | 34.7% | -5.73% |
| TIGHT | 275 | 47.6% | -0.15% | 42.2% | -2.46% | 40.7% | -0.24% |
| BELOW85 | 154 | 38.3% | -1.81% | 37.7% | -3.23% | 27.3% | -5.56% |
| PULLBACK | 54 | 37.0% | -1.36% | 44.4% | -2.63% | 53.7% | 2.99% |
| EARLY | 48 | 43.8% | -1.1% | 35.4% | -3.72% | 39.6% | -3.91% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 675 | 43.5% | -0.81% | 38.7% | -3.91% | 37.1% | -3.27% |
| <85 | 271 | 38.0% | -1.77% | 41.7% | -3.06% | 29.5% | -6.54% |
| 90-94 | 175 | 42.9% | -1.75% | 47.4% | -2.21% | 45.1% | -2.36% |
| 85-89 | 147 | 42.9% | -0.54% | 43.5% | -2.27% | 32.7% | -5.21% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 85 | 47.1% | -0.22% | 45.9% | -1.66% | 43.5% | -1.35% |
| lifted (0..+5) | 366 | 44.0% | -0.7% | 37.7% | -3.33% | 33.6% | -3.31% |
| extended (>+5) | 737 | 41.2% | -1.31% | 41.6% | -3.66% | 34.7% | -5.73% |
| pullback (-5..-2) | 47 | 38.3% | -1.29% | 46.8% | -1.17% | 48.9% | 1.61% |
| deep-pb (<-5) | 33 | 36.4% | -3.32% | 48.5% | -2.41% | 57.6% | 9.06% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 529 | 40.8% | -1.07% | 42.0% | -2.99% | 36.5% | -5.04% |
| 30-49% | 512 | 42.6% | -1.23% | 38.5% | -3.82% | 30.1% | -5.84% |
| 50+% | 227 | 44.4% | -0.97% | 45.3% | -2.85% | 48.9% | 2.27% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 338 | 60.8% | 8.53% |
| Energy Minerals | 23 | 78.3% | 7.9% |
| Commercial Services | 7 | 57.1% | 4.4% |
| Producer Manufacturing | 16 | 50.0% | 0.93% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Consumer Services | 18 | 38.9% | -0.61% |
| Health Services | 21 | 19.0% | -2.68% |
| Technology Services | 309 | 40.5% | -4.97% |
| Industrial Services | 19 | 10.5% | -5.82% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Non-Energy Minerals | 147 | 16.3% | -11.0% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.62 | +70.0% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 13.31 | +63.5% |
| IOVA | 09-03 | EXTENDED | 98.8 | +110.2% | 8.70 | 14.22 | +63.5% |
| IOVA | 09-04 | EXTENDED | 98.7 | +98.2% | 8.79 | 14.15 | +61.0% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |
| IOVA | 09-14 | TIGHT | 99.0 | +32.5% | 9.26 | 14.56 | +57.2% |
| MRNA | 09-11 | TIGHT | 99.7 | +126.9% | 143.97 | 225.00 | +56.3% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 14.71 | -61.9% |
| RIOT | 09-24 | EXTENDED | 83.7 | +23.3% | 23.48 | 12.89 | -45.1% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| CLSK | 09-25 | BELOW85 | 68.4 | +20.1% | 13.95 | 7.88 | -43.5% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 61.21 | -42.9% |
| CLSK | 09-24 | BELOW85 | 65.6 | +22.0% | 14.26 | 8.15 | -42.9% |
| CLSK | 09-21 | EXTENDED | 66.1 | +23.3% | 14.76 | 8.46 | -42.7% |
| KEEL | 09-24 | EXTENDED | 80.4 | +23.4% | 3.90 | 2.24 | -42.6% |
| RIOT | 09-21 | EXTENDED | 77.9 | +25.8% | 24.18 | 13.97 | -42.2% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
