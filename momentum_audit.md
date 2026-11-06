# Momentum Scan Performance Audit — 2026-11-06

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1173. With forward data: 1173.

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
| EXTENDED | 661 | 39.0% | -2.16% | 39.0% | -4.55% | 31.8% | -7.57% |
| TIGHT | 265 | 46.0% | -0.61% | 41.1% | -3.07% | 39.2% | -2.14% |
| BELOW85 | 148 | 35.8% | -2.24% | 35.1% | -3.7% | 24.3% | -6.57% |
| PULLBACK | 52 | 34.6% | -2.08% | 42.3% | -3.11% | 51.9% | 2.34% |
| EARLY | 47 | 42.6% | -1.47% | 36.2% | -3.75% | 38.3% | -4.38% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 623 | 41.1% | -1.63% | 36.8% | -4.64% | 35.0% | -5.04% |
| <85 | 250 | 34.4% | -2.74% | 37.6% | -4.08% | 24.4% | -8.23% |
| 90-94 | 164 | 43.9% | -1.69% | 46.3% | -2.73% | 44.5% | -3.57% |
| 85-89 | 136 | 41.9% | -0.88% | 43.4% | -2.58% | 31.6% | -6.21% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 82 | 45.1% | -0.48% | 43.9% | -2.08% | 41.5% | -2.4% |
| lifted (0..+5) | 352 | 42.0% | -1.21% | 36.4% | -3.91% | 31.5% | -5.0% |
| extended (>+5) | 661 | 39.0% | -2.16% | 39.0% | -4.55% | 31.8% | -7.57% |
| pullback (-5..-2) | 46 | 37.0% | -1.62% | 45.7% | -1.31% | 47.8% | 1.26% |
| deep-pb (<-5) | 32 | 34.4% | -4.09% | 46.9% | -2.92% | 56.2% | 8.61% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 474 | 37.1% | -2.1% | 38.4% | -4.24% | 32.7% | -7.29% |
| 30-49% | 484 | 41.5% | -1.7% | 37.2% | -4.25% | 29.1% | -7.07% |
| 50+% | 215 | 43.7% | -1.31% | 44.7% | -2.98% | 46.0% | 1.16% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 318 | 58.2% | 7.08% |
| Energy Minerals | 14 | 64.3% | 2.88% |
| Consumer Services | 11 | 54.5% | 1.33% |
| Producer Manufacturing | 15 | 46.7% | -3.21% |
| Health Services | 21 | 14.3% | -3.44% |
| Retail Trade | 11 | 0.0% | -6.22% |
| Technology Services | 285 | 38.2% | -6.52% |
| Commercial Services | 2 | 0.0% | -6.91% |
| Industrial Services | 17 | 0.0% | -8.06% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Non-Energy Minerals | 143 | 14.0% | -11.44% |
| Electronic Technology | 295 | 18.3% | -14.99% |

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
