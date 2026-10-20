# Momentum Scan Performance Audit — 2026-10-20

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1370. With forward data: 1370.

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
| EXTENDED | 770 | 42.0% | -1.19% | 42.6% | -3.2% | 33.0% | -5.53% |
| TIGHT | 309 | 49.8% | 0.23% | 45.6% | -0.88% | 42.7% | 0.43% |
| BELOW85 | 178 | 42.7% | -0.95% | 45.5% | -0.73% | 34.8% | -2.74% |
| PULLBACK | 63 | 42.9% | -1.09% | 50.8% | -1.3% | 60.3% | 6.18% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.88% | 40.0% | -4.29% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 723 | 45.0% | -0.62% | 40.8% | -3.1% | 36.5% | -2.78% |
| <85 | 300 | 41.0% | -1.14% | 46.7% | -1.38% | 34.7% | -4.39% |
| 90-94 | 195 | 45.1% | -1.38% | 50.8% | -0.78% | 47.7% | -1.21% |
| 85-89 | 152 | 44.1% | -0.41% | 44.1% | -1.85% | 30.3% | -5.53% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 100 | 48.0% | 0.37% | 48.0% | -0.0% | 46.0% | 0.51% |
| lifted (0..+5) | 404 | 47.3% | -0.3% | 42.6% | -1.74% | 36.9% | -2.36% |
| extended (>+5) | 770 | 42.0% | -1.19% | 42.6% | -3.2% | 33.0% | -5.53% |
| pullback (-5..-2) | 55 | 43.6% | -0.57% | 52.7% | 1.63% | 54.5% | 4.02% |
| deep-pb (<-5) | 41 | 41.5% | -2.35% | 58.5% | -0.42% | 65.9% | 12.2% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 584 | 43.5% | -0.64% | 46.1% | -1.49% | 39.2% | -3.61% |
| 30-49% | 543 | 44.0% | -1.04% | 40.3% | -2.96% | 31.5% | -4.96% |
| 50+% | 243 | 45.5% | -0.76% | 46.8% | -2.52% | 44.2% | 1.79% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 382 | 57.3% | 8.56% |
| Energy Minerals | 32 | 78.1% | 7.84% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | -0.03% |
| Health Services | 22 | 18.2% | -0.99% |
| Consumer Services | 21 | 33.3% | -1.29% |
| Industrial Services | 23 | 26.1% | -3.15% |
| Technology Services | 340 | 43.8% | -3.93% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Non-Energy Minerals | 147 | 16.3% | -11.0% |

## Top 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| IOVA | 09-01 | TIGHT | 98.9 | +84.4% | 8.28 | 14.82 | +79.0% |
| IOVA | 08-31 | TIGHT | 98.4 | +69.3% | 8.17 | 14.45 | +76.9% |
| IOVA | 07-23 | EXTENDED | 94.2 | +31.9% | 5.13 | 8.99 | +75.2% |
| IOVA | 09-11 | PULLBACK | 98.8 | +25.6% | 8.60 | 14.62 | +70.0% |
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 13.31 | +63.5% |
| IOVA | 09-03 | EXTENDED | 98.8 | +110.2% | 8.70 | 14.22 | +63.5% |
| IOVA | 09-04 | EXTENDED | 98.7 | +98.2% | 8.79 | 14.15 | +61.0% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |

## Bottom 10 — 20d Returns

| Ticker | Date | Setup | RS | 1M% | Scan$ | 20d$ | Return |
|---|---|---|---:|---:|---:|---:|---:|
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 15.23 | -60.6% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.31 | -46.9% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 18.31 | -46.2% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 18.31 | -45.3% |
| QMCO | 09-29 | EXTENDED | 99.8 | +34.1% | 32.86 | 18.31 | -44.3% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| CLSK | 09-21 | EXTENDED | 66.1 | +23.3% | 14.76 | 8.46 | -42.7% |
| QMCO | 10-01 | EXTENDED | 99.8 | +44.4% | 31.89 | 18.31 | -42.6% |
| QMCO | 09-30 | EXTENDED | 99.8 | +40.3% | 31.72 | 18.31 | -42.3% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
