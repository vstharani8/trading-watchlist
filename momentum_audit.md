# Momentum Scan Performance Audit — 2026-11-03

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1224. With forward data: 1224.

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
| EXTENDED | 704 | 40.2% | -1.6% | 40.1% | -4.12% | 32.5% | -7.18% |
| TIGHT | 269 | 46.8% | -0.47% | 41.3% | -2.92% | 39.4% | -2.13% |
| BELOW85 | 149 | 36.2% | -2.17% | 35.6% | -3.62% | 24.8% | -6.5% |
| PULLBACK | 54 | 37.0% | -1.36% | 44.4% | -2.63% | 53.7% | 2.99% |
| EARLY | 48 | 43.8% | -1.1% | 35.4% | -3.72% | 39.6% | -4.29% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 651 | 42.2% | -1.19% | 37.3% | -4.39% | 35.3% | -4.92% |
| <85 | 257 | 35.8% | -2.27% | 38.5% | -3.66% | 25.7% | -7.83% |
| 90-94 | 170 | 43.5% | -1.58% | 47.6% | -2.49% | 44.7% | -3.44% |
| 85-89 | 146 | 43.2% | -0.51% | 43.8% | -2.25% | 32.9% | -5.75% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 83 | 45.8% | -0.47% | 44.6% | -1.93% | 42.2% | -2.32% |
| lifted (0..+5) | 357 | 42.9% | -1.03% | 36.4% | -3.78% | 31.9% | -4.95% |
| extended (>+5) | 704 | 40.2% | -1.6% | 40.1% | -4.12% | 32.5% | -7.18% |
| pullback (-5..-2) | 47 | 38.3% | -1.29% | 46.8% | -1.17% | 48.9% | 1.58% |
| deep-pb (<-5) | 33 | 36.4% | -3.32% | 48.5% | -2.41% | 57.6% | 9.06% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 503 | 38.8% | -1.62% | 39.4% | -3.79% | 34.0% | -6.84% |
| 30-49% | 501 | 42.1% | -1.34% | 38.1% | -3.95% | 29.5% | -6.8% |
| 50+% | 220 | 44.5% | -0.97% | 44.5% | -3.02% | 45.9% | 0.95% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 327 | 58.4% | 7.23% |
| Energy Minerals | 16 | 68.8% | 5.0% |
| Consumer Services | 14 | 50.0% | 0.62% |
| Producer Manufacturing | 16 | 50.0% | -1.72% |
| Commercial Services | 4 | 25.0% | -3.41% |
| Health Services | 21 | 14.3% | -3.79% |
| Retail Trade | 12 | 0.0% | -5.97% |
| Technology Services | 297 | 38.7% | -6.26% |
| Industrial Services | 17 | 0.0% | -8.35% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Non-Energy Minerals | 147 | 16.3% | -11.0% |
| Electronic Technology | 311 | 18.6% | -14.73% |

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
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 16.73 | -50.0% |
| FCEL | 10-06 | EXTENDED | 95.1 | +24.4% | 20.65 | 10.50 | -49.1% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 54.89 | -48.8% |
| INTC | 10-05 | TIGHT | 98.5 | +34.3% | 116.19 | 59.97 | -48.4% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.27 | -47.0% |
| INTC | 10-06 | TIGHT | 97.5 | +25.7% | 112.50 | 59.97 | -46.7% |
| RIOT | 09-24 | EXTENDED | 83.7 | +23.3% | 23.48 | 12.89 | -45.1% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
