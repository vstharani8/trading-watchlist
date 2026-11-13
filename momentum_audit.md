# Momentum Scan Performance Audit — 2026-11-13

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 937. With forward data: 937.

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
| EXTENDED | 463 | 38.4% | -3.06% | 35.4% | -5.71% | 31.5% | -8.48% |
| TIGHT | 246 | 44.7% | -0.82% | 38.2% | -3.54% | 39.4% | -2.36% |
| BELOW85 | 135 | 37.8% | -1.96% | 36.3% | -3.56% | 26.7% | -6.58% |
| PULLBACK | 49 | 32.7% | -2.49% | 38.8% | -3.83% | 49.0% | 1.98% |
| EARLY | 44 | 40.9% | -1.78% | 34.1% | -4.11% | 36.4% | -4.5% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 505 | 40.4% | -2.17% | 36.8% | -4.92% | 36.0% | -5.15% |
| <85 | 214 | 33.6% | -3.43% | 36.0% | -4.67% | 25.7% | -8.54% |
| 90-94 | 119 | 47.1% | -1.25% | 39.5% | -3.82% | 44.5% | -3.44% |
| 85-89 | 99 | 41.4% | -1.09% | 31.3% | -4.28% | 29.3% | -6.68% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 75 | 45.3% | -0.63% | 41.3% | -2.51% | 41.3% | -2.41% |
| lifted (0..+5) | 324 | 41.7% | -1.24% | 34.9% | -4.17% | 32.4% | -5.24% |
| extended (>+5) | 463 | 38.4% | -3.06% | 35.4% | -5.71% | 31.5% | -8.48% |
| pullback (-5..-2) | 45 | 35.6% | -1.96% | 44.4% | -1.45% | 46.7% | 0.93% |
| deep-pb (<-5) | 30 | 33.3% | -4.37% | 43.3% | -3.81% | 53.3% | 8.91% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 361 | 35.7% | -2.6% | 36.0% | -5.01% | 32.7% | -8.13% |
| 30-49% | 390 | 42.6% | -2.02% | 33.8% | -4.94% | 28.2% | -7.66% |
| 50+% | 186 | 41.9% | -1.92% | 42.5% | -3.36% | 48.9% | 2.28% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 272 | 57.7% | 6.54% |
| Consumer Services | 4 | 50.0% | 2.3% |
| Energy Minerals | 8 | 50.0% | -2.08% |
| Health Services | 17 | 17.6% | -2.26% |
| Producer Manufacturing | 13 | 46.2% | -4.84% |
| Retail Trade | 10 | 0.0% | -6.53% |
| Technology Services | 225 | 39.1% | -6.7% |
| Industrial Services | 11 | 0.0% | -9.03% |
| Consumer Non-Durables | 7 | 0.0% | -11.25% |
| Process Industries | 1 | 0.0% | -12.28% |
| Non-Energy Minerals | 117 | 7.7% | -13.68% |
| Electronic Technology | 229 | 21.0% | -14.67% |

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
| IOVA | 09-14 | TIGHT | 99.0 | +32.5% | 9.26 | 14.56 | +57.2% |
| MRNA | 09-11 | TIGHT | 99.7 | +126.9% | 143.97 | 225.00 | +56.3% |
| TXG | 09-04 | TIGHT | 99.5 | +34.4% | 62.65 | 97.74 | +56.0% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 11.70 | -69.7% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 16.73 | -50.8% |
| AEHR | 10-05 | EXTENDED | 98.8 | +37.3% | 104.40 | 51.47 | -50.7% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 54.89 | -48.8% |
| INTC | 10-05 | TIGHT | 98.5 | +34.3% | 116.19 | 59.97 | -48.4% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 17.67 | -47.2% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.27 | -47.0% |
| INTC | 10-06 | TIGHT | 97.5 | +25.7% | 112.50 | 60.55 | -46.2% |
| FCEL | 10-06 | EXTENDED | 95.1 | +24.4% | 20.65 | 11.21 | -45.7% |
| RIOT | 09-24 | EXTENDED | 83.7 | +23.3% | 23.48 | 12.89 | -45.1% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
