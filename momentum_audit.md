# Momentum Scan Performance Audit — 2026-11-23

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 669. With forward data: 668.

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
| EXTENDED | 321 | 38.6% | -2.9% | 33.6% | -6.2% | 29.9% | -9.96% |
| TIGHT | 190 | 42.6% | -1.24% | 37.9% | -3.53% | 37.9% | -2.75% |
| BELOW85 | 99 | 38.4% | -2.79% | 36.4% | -3.9% | 23.2% | -7.82% |
| PULLBACK | 30 | 40.0% | 0.1% | 50.0% | 0.58% | 56.7% | 5.64% |
| EARLY | 28 | 39.3% | -1.46% | 35.7% | -2.54% | 42.9% | -2.05% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 378 | 44.2% | -1.27% | 40.2% | -3.83% | 35.4% | -5.75% |
| <85 | 148 | 33.1% | -4.02% | 34.5% | -5.07% | 25.0% | -9.41% |
| 90-94 | 77 | 41.6% | -2.55% | 33.8% | -5.78% | 39.0% | -4.47% |
| 85-89 | 65 | 27.7% | -3.23% | 18.5% | -7.08% | 29.2% | -7.29% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 57 | 43.9% | -2.08% | 42.1% | -2.14% | 38.6% | -3.21% |
| lifted (0..+5) | 237 | 40.1% | -1.54% | 33.8% | -4.39% | 30.8% | -5.88% |
| extended (>+5) | 321 | 38.6% | -2.9% | 33.6% | -6.2% | 29.9% | -9.96% |
| pullback (-5..-2) | 36 | 38.9% | -1.29% | 50.0% | 0.33% | 44.4% | 1.46% |
| deep-pb (<-5) | 17 | 47.1% | -1.15% | 64.7% | 2.39% | 76.5% | 19.97% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 275 | 36.0% | -2.85% | 37.1% | -5.45% | 30.9% | -9.56% |
| 30-49% | 271 | 43.5% | -1.6% | 32.5% | -4.75% | 26.6% | -8.4% |
| 50+% | 122 | 40.2% | -2.16% | 41.8% | -2.6% | 51.6% | 4.26% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 210 | 58.1% | 7.56% |
| Energy Minerals | 3 | 33.3% | -0.64% |
| Consumer Services | 2 | 0.0% | -3.52% |
| Health Services | 11 | 9.1% | -3.63% |
| Retail Trade | 8 | 0.0% | -5.56% |
| Producer Manufacturing | 8 | 50.0% | -5.56% |
| Industrial Services | 10 | 0.0% | -8.9% |
| Technology Services | 156 | 33.3% | -9.1% |
| Process Industries | 1 | 0.0% | -12.28% |
| Electronic Technology | 162 | 21.6% | -15.94% |
| Non-Energy Minerals | 73 | 4.1% | -17.36% |
| Consumer Non-Durables | 1 | 0.0% | -17.94% |

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
