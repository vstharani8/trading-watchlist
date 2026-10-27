# Momentum Scan Performance Audit — 2026-10-27

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1286. With forward data: 1286.

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
| EXTENDED | 748 | 41.5% | -1.24% | 41.9% | -3.47% | 32.5% | -6.36% |
| TIGHT | 278 | 47.5% | -0.23% | 42.8% | -2.36% | 39.6% | -0.96% |
| BELOW85 | 156 | 38.5% | -1.78% | 37.8% | -3.11% | 27.6% | -5.46% |
| PULLBACK | 54 | 37.0% | -1.36% | 44.4% | -2.63% | 53.7% | 2.89% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.88% | 40.0% | -4.78% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 685 | 43.7% | -0.81% | 39.3% | -3.72% | 34.6% | -4.24% |
| <85 | 275 | 38.5% | -1.63% | 42.2% | -2.85% | 30.2% | -6.26% |
| 90-94 | 178 | 42.7% | -1.73% | 47.2% | -2.18% | 44.9% | -2.63% |
| 85-89 | 148 | 43.2% | -0.52% | 43.9% | -2.1% | 30.4% | -5.75% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 85 | 47.1% | -0.22% | 45.9% | -1.66% | 42.4% | -1.29% |
| lifted (0..+5) | 373 | 44.2% | -0.74% | 38.6% | -3.09% | 33.5% | -3.87% |
| extended (>+5) | 748 | 41.5% | -1.24% | 41.9% | -3.47% | 32.5% | -6.36% |
| pullback (-5..-2) | 47 | 38.3% | -1.29% | 46.8% | -1.17% | 46.8% | 1.08% |
| deep-pb (<-5) | 33 | 36.4% | -3.32% | 48.5% | -2.41% | 57.6% | 9.06% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 538 | 41.3% | -1.05% | 42.6% | -2.76% | 35.9% | -5.53% |
| 30-49% | 518 | 42.9% | -1.14% | 39.0% | -3.64% | 29.5% | -6.34% |
| 50+% | 230 | 44.2% | -1.03% | 45.1% | -2.84% | 43.3% | 1.51% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 344 | 55.9% | 7.44% |
| Energy Minerals | 26 | 73.1% | 6.83% |
| Commercial Services | 8 | 62.5% | 6.65% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | -0.21% |
| Consumer Services | 20 | 35.0% | -1.24% |
| Health Services | 21 | 14.3% | -3.73% |
| Technology Services | 315 | 41.0% | -4.89% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Industrial Services | 19 | 10.5% | -8.49% |
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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 15.00 | -61.2% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 56.60 | -47.2% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.69 | -45.8% |
| AEHR | 10-05 | EXTENDED | 98.8 | +37.3% | 104.40 | 56.60 | -45.8% |
| RIOT | 09-24 | EXTENDED | 83.7 | +23.3% | 23.48 | 12.89 | -45.1% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 18.69 | -45.0% |
| FCEL | 10-06 | EXTENDED | 95.1 | +24.4% | 20.65 | 11.46 | -44.5% |
| AEHR | 10-01 | TIGHT | 98.7 | +22.5% | 101.60 | 56.60 | -44.3% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 18.69 | -44.2% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
