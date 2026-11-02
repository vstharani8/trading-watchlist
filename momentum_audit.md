# Momentum Scan Performance Audit — 2026-11-02

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1240. With forward data: 1240.

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
| EXTENDED | 717 | 40.8% | -1.47% | 40.6% | -3.9% | 33.1% | -6.61% |
| TIGHT | 272 | 47.1% | -0.35% | 41.5% | -2.72% | 39.7% | -1.47% |
| BELOW85 | 149 | 36.2% | -2.17% | 35.6% | -3.62% | 24.8% | -6.47% |
| PULLBACK | 54 | 37.0% | -1.36% | 44.4% | -2.63% | 53.7% | 2.99% |
| EARLY | 48 | 43.8% | -1.1% | 35.4% | -3.72% | 39.6% | -4.24% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 660 | 42.8% | -1.04% | 37.6% | -4.25% | 35.7% | -4.38% |
| <85 | 261 | 36.4% | -2.19% | 39.5% | -3.47% | 26.8% | -7.57% |
| 90-94 | 172 | 43.6% | -1.54% | 48.3% | -2.02% | 44.8% | -2.77% |
| 85-89 | 147 | 42.9% | -0.54% | 43.5% | -2.27% | 32.7% | -5.46% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 83 | 45.8% | -0.47% | 44.6% | -1.93% | 42.2% | -2.18% |
| lifted (0..+5) | 360 | 43.1% | -0.93% | 36.7% | -3.62% | 32.2% | -4.42% |
| extended (>+5) | 717 | 40.8% | -1.47% | 40.6% | -3.9% | 33.1% | -6.61% |
| pullback (-5..-2) | 47 | 38.3% | -1.29% | 46.8% | -1.17% | 48.9% | 1.42% |
| deep-pb (<-5) | 33 | 36.4% | -3.32% | 48.5% | -2.41% | 57.6% | 9.06% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 513 | 39.4% | -1.49% | 40.2% | -3.45% | 34.7% | -6.2% |
| 30-49% | 505 | 42.4% | -1.23% | 38.2% | -3.89% | 29.7% | -6.54% |
| 50+% | 222 | 44.8% | -0.96% | 44.8% | -2.97% | 46.2% | 1.57% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 332 | 59.2% | 7.85% |
| Energy Minerals | 17 | 70.6% | 6.11% |
| Consumer Services | 15 | 46.7% | 0.5% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | 0.04% |
| Commercial Services | 5 | 40.0% | -1.29% |
| Health Services | 21 | 14.3% | -3.27% |
| Technology Services | 300 | 39.0% | -5.94% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Industrial Services | 17 | 0.0% | -7.54% |
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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 14.20 | -63.3% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 54.89 | -48.8% |
| AEHR | 10-05 | EXTENDED | 98.8 | +37.3% | 104.40 | 54.89 | -47.4% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.27 | -47.0% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 18.27 | -46.3% |
| FCEL | 10-06 | EXTENDED | 95.1 | +24.4% | 20.65 | 11.22 | -45.7% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 18.27 | -45.4% |
| RIOT | 09-24 | EXTENDED | 83.7 | +23.3% | 23.48 | 12.89 | -45.1% |
| INTC | 10-02 | TIGHT | 98.7 | +38.2% | 119.33 | 65.76 | -44.9% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
