# Momentum Scan Performance Audit — 2026-11-04

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1206. With forward data: 1206.

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
| EXTENDED | 691 | 39.5% | -1.86% | 39.4% | -4.41% | 32.0% | -7.33% |
| TIGHT | 267 | 46.4% | -0.59% | 41.2% | -3.08% | 39.3% | -2.19% |
| BELOW85 | 148 | 35.8% | -2.24% | 35.1% | -3.7% | 24.3% | -6.57% |
| PULLBACK | 53 | 35.8% | -1.78% | 43.4% | -2.95% | 52.8% | 2.6% |
| EARLY | 47 | 42.6% | -1.47% | 36.2% | -3.75% | 38.3% | -4.38% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 642 | 41.7% | -1.41% | 36.6% | -4.65% | 34.9% | -4.98% |
| <85 | 254 | 35.0% | -2.49% | 37.8% | -3.94% | 24.8% | -8.1% |
| 90-94 | 169 | 43.2% | -1.68% | 47.3% | -2.56% | 44.4% | -3.52% |
| 85-89 | 141 | 41.8% | -0.83% | 44.7% | -2.32% | 32.6% | -5.93% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 83 | 45.8% | -0.47% | 44.6% | -1.93% | 42.2% | -2.3% |
| lifted (0..+5) | 353 | 42.2% | -1.19% | 36.3% | -3.95% | 31.4% | -5.05% |
| extended (>+5) | 691 | 39.5% | -1.86% | 39.4% | -4.41% | 32.0% | -7.33% |
| pullback (-5..-2) | 47 | 38.3% | -1.29% | 46.8% | -1.17% | 48.9% | 1.58% |
| deep-pb (<-5) | 32 | 34.4% | -4.09% | 46.9% | -2.92% | 56.2% | 8.61% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 492 | 37.8% | -1.91% | 38.6% | -4.17% | 32.9% | -7.15% |
| 30-49% | 495 | 41.6% | -1.57% | 37.8% | -4.09% | 29.5% | -6.86% |
| 50+% | 219 | 44.3% | -1.02% | 44.3% | -3.06% | 45.7% | 1.02% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 324 | 58.0% | 7.16% |
| Energy Minerals | 15 | 66.7% | 3.77% |
| Consumer Services | 12 | 58.3% | 1.7% |
| Producer Manufacturing | 16 | 50.0% | -1.74% |
| Health Services | 21 | 14.3% | -3.44% |
| Retail Trade | 12 | 0.0% | -5.97% |
| Technology Services | 291 | 37.8% | -6.57% |
| Commercial Services | 3 | 0.0% | -6.91% |
| Industrial Services | 17 | 0.0% | -8.06% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Non-Energy Minerals | 147 | 16.3% | -11.0% |
| Electronic Technology | 306 | 18.3% | -14.79% |

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
