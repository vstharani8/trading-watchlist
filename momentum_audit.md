# Momentum Scan Performance Audit — 2026-11-18

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 764. With forward data: 764.

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
| EXTENDED | 370 | 37.3% | -2.89% | 33.5% | -5.74% | 31.4% | -8.64% |
| TIGHT | 208 | 43.3% | -1.13% | 38.0% | -3.54% | 38.0% | -2.86% |
| BELOW85 | 114 | 36.8% | -2.08% | 35.1% | -3.73% | 24.6% | -7.23% |
| PULLBACK | 39 | 33.3% | -1.9% | 41.0% | -1.37% | 56.4% | 4.75% |
| EARLY | 33 | 39.4% | -1.2% | 30.3% | -3.17% | 39.4% | -2.88% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 421 | 41.8% | -1.62% | 39.4% | -3.94% | 36.6% | -5.06% |
| <85 | 174 | 32.2% | -3.43% | 33.9% | -4.69% | 25.3% | -8.7% |
| 90-94 | 90 | 43.3% | -1.95% | 34.4% | -4.83% | 42.2% | -3.44% |
| 85-89 | 79 | 31.6% | -2.5% | 16.5% | -6.7% | 27.8% | -7.27% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 63 | 46.0% | -1.0% | 41.3% | -2.33% | 39.7% | -2.88% |
| lifted (0..+5) | 266 | 39.8% | -1.32% | 33.5% | -4.23% | 30.8% | -5.81% |
| extended (>+5) | 370 | 37.3% | -2.89% | 33.5% | -5.74% | 31.4% | -8.64% |
| pullback (-5..-2) | 40 | 35.0% | -2.07% | 45.0% | -0.55% | 47.5% | 1.8% |
| deep-pb (<-5) | 25 | 36.0% | -3.54% | 48.0% | -0.94% | 64.0% | 13.03% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 304 | 33.2% | -3.04% | 35.2% | -5.31% | 30.3% | -9.24% |
| 30-49% | 314 | 42.7% | -1.68% | 32.2% | -4.61% | 27.7% | -7.63% |
| 50+% | 146 | 41.8% | -1.39% | 41.8% | -2.6% | 54.1% | 4.65% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 239 | 57.7% | 7.04% |
| Health Services | 15 | 13.3% | -3.11% |
| Energy Minerals | 4 | 25.0% | -3.27% |
| Consumer Services | 2 | 0.0% | -3.52% |
| Producer Manufacturing | 8 | 50.0% | -5.56% |
| Retail Trade | 10 | 0.0% | -6.53% |
| Technology Services | 181 | 35.9% | -7.8% |
| Industrial Services | 10 | 0.0% | -8.9% |
| Process Industries | 1 | 0.0% | -12.28% |
| Consumer Non-Durables | 3 | 0.0% | -14.45% |
| Electronic Technology | 174 | 24.1% | -14.76% |
| Non-Energy Minerals | 94 | 4.3% | -15.55% |

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
