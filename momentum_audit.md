# Momentum Scan Performance Audit — 2026-11-24

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 640. With forward data: 640.

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
| EXTENDED | 306 | 38.2% | -2.93% | 34.3% | -6.08% | 29.7% | -10.31% |
| TIGHT | 184 | 42.9% | -1.23% | 38.0% | -3.46% | 37.0% | -2.89% |
| BELOW85 | 95 | 38.9% | -2.79% | 37.9% | -3.54% | 24.2% | -7.67% |
| PULLBACK | 28 | 42.9% | 1.24% | 50.0% | 0.95% | 50.0% | 4.79% |
| EARLY | 27 | 40.7% | -1.45% | 37.0% | -2.28% | 44.4% | -1.52% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 366 | 44.5% | -1.17% | 40.7% | -3.67% | 35.0% | -5.99% |
| <85 | 141 | 32.6% | -4.16% | 35.5% | -4.95% | 25.5% | -9.36% |
| 90-94 | 74 | 40.5% | -2.73% | 33.8% | -5.82% | 37.8% | -4.67% |
| 85-89 | 59 | 28.8% | -3.01% | 18.6% | -6.76% | 27.1% | -7.87% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 53 | 45.3% | -1.83% | 43.4% | -1.7% | 37.7% | -3.65% |
| lifted (0..+5) | 230 | 40.4% | -1.58% | 34.3% | -4.26% | 30.9% | -5.78% |
| extended (>+5) | 306 | 38.2% | -2.93% | 34.3% | -6.08% | 29.7% | -10.31% |
| pullback (-5..-2) | 33 | 42.4% | -0.37% | 51.5% | 0.73% | 39.4% | 0.66% |
| deep-pb (<-5) | 18 | 44.4% | -1.22% | 61.1% | 2.08% | 72.2% | 18.63% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 271 | 36.2% | -2.74% | 37.6% | -5.34% | 31.0% | -9.64% |
| 30-49% | 257 | 44.4% | -1.55% | 32.7% | -4.72% | 25.3% | -8.62% |
| 50+% | 112 | 39.3% | -2.26% | 43.8% | -1.87% | 52.7% | 4.52% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 200 | 58.0% | 7.73% |
| Energy Minerals | 3 | 33.3% | -0.64% |
| Consumer Services | 2 | 0.0% | -3.52% |
| Health Services | 10 | 10.0% | -3.69% |
| Retail Trade | 7 | 0.0% | -5.49% |
| Producer Manufacturing | 8 | 50.0% | -5.56% |
| Industrial Services | 10 | 0.0% | -8.9% |
| Technology Services | 147 | 32.7% | -9.59% |
| Process Industries | 1 | 0.0% | -12.28% |
| Electronic Technology | 160 | 21.2% | -16.21% |
| Non-Energy Minerals | 69 | 2.9% | -17.25% |
| Finance | 23 | 8.7% | -19.33% |

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
