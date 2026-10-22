# Momentum Scan Performance Audit — 2026-10-22

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1350. With forward data: 1350.

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
| EXTENDED | 763 | 42.0% | -1.15% | 42.8% | -3.26% | 33.5% | -5.64% |
| TIGHT | 303 | 49.5% | 0.15% | 45.5% | -0.97% | 42.6% | 0.42% |
| BELOW85 | 176 | 42.0% | -1.04% | 44.9% | -0.96% | 34.1% | -3.05% |
| PULLBACK | 58 | 41.4% | -0.99% | 48.3% | -2.27% | 56.9% | 4.62% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.88% | 40.0% | -4.17% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 715 | 45.0% | -0.62% | 40.9% | -3.13% | 36.8% | -2.77% |
| <85 | 297 | 40.7% | -1.16% | 46.5% | -1.5% | 34.3% | -4.55% |
| 90-94 | 188 | 44.7% | -1.37% | 50.0% | -1.26% | 46.8% | -2.38% |
| 85-89 | 150 | 43.3% | -0.47% | 44.0% | -2.03% | 30.0% | -5.69% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 99 | 47.5% | 0.31% | 47.5% | -0.2% | 45.5% | 0.29% |
| lifted (0..+5) | 398 | 47.0% | -0.37% | 42.5% | -1.81% | 36.7% | -2.42% |
| extended (>+5) | 763 | 42.0% | -1.15% | 42.8% | -3.26% | 33.5% | -5.64% |
| pullback (-5..-2) | 51 | 43.1% | -0.31% | 51.0% | 1.07% | 51.0% | 2.9% |
| deep-pb (<-5) | 39 | 38.5% | -2.74% | 56.4% | -1.33% | 64.1% | 11.19% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 576 | 42.9% | -0.7% | 45.3% | -1.73% | 38.4% | -3.87% |
| 30-49% | 535 | 44.3% | -0.96% | 40.7% | -3.0% | 31.6% | -5.19% |
| 50+% | 239 | 45.0% | -0.85% | 46.8% | -2.58% | 45.5% | 1.73% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 15 | 80.0% | 9.63% |
| Health Technology | 370 | 58.3% | 8.68% |
| Energy Minerals | 31 | 77.4% | 7.45% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | -0.16% |
| Consumer Services | 21 | 33.3% | -1.13% |
| Health Services | 21 | 14.3% | -3.79% |
| Technology Services | 337 | 43.9% | -4.02% |
| Industrial Services | 22 | 22.7% | -4.57% |
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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 14.85 | -61.6% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.99 | -45.0% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 18.99 | -44.2% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 18.99 | -43.3% |
| CLSK | 09-21 | EXTENDED | 66.1 | +23.3% | 14.76 | 8.46 | -42.7% |
| RIOT | 09-21 | EXTENDED | 77.9 | +25.8% | 24.18 | 13.97 | -42.2% |
| QMCO | 09-29 | EXTENDED | 99.8 | +34.1% | 32.86 | 18.99 | -42.2% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 61.99 | -42.2% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
