# Momentum Scan Performance Audit — 2026-10-19

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1383. With forward data: 1383.

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
| EXTENDED | 774 | 41.8% | -1.22% | 42.6% | -3.34% | 32.9% | -5.88% |
| TIGHT | 314 | 49.4% | 0.13% | 45.9% | -0.96% | 43.0% | 0.11% |
| BELOW85 | 179 | 43.0% | -0.94% | 45.8% | -0.65% | 35.2% | -2.72% |
| PULLBACK | 66 | 42.4% | -1.19% | 53.0% | -0.85% | 62.1% | 6.43% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.92% | 40.0% | -5.03% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 730 | 44.6% | -0.69% | 40.9% | -3.23% | 36.6% | -3.24% |
| <85 | 302 | 41.1% | -1.17% | 46.7% | -1.39% | 34.8% | -4.41% |
| 90-94 | 198 | 45.6% | -1.35% | 51.8% | -0.7% | 48.7% | -1.18% |
| 85-89 | 153 | 43.8% | -0.43% | 44.4% | -1.88% | 30.1% | -5.62% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 102 | 48.0% | 0.34% | 49.0% | 0.13% | 47.1% | 0.66% |
| lifted (0..+5) | 408 | 47.1% | -0.37% | 42.6% | -1.8% | 37.0% | -2.71% |
| extended (>+5) | 774 | 41.8% | -1.22% | 42.6% | -3.34% | 32.9% | -5.88% |
| pullback (-5..-2) | 56 | 44.6% | -0.56% | 53.6% | 1.75% | 55.4% | 3.97% |
| deep-pb (<-5) | 43 | 39.5% | -2.47% | 60.5% | 0.02% | 67.4% | 12.43% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 589 | 43.5% | -0.67% | 46.3% | -1.49% | 39.4% | -3.82% |
| 30-49% | 548 | 43.8% | -1.08% | 40.7% | -3.02% | 31.9% | -5.15% |
| 50+% | 246 | 45.1% | -0.84% | 46.4% | -2.73% | 43.8% | 1.31% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 390 | 57.3% | 8.22% |
| Energy Minerals | 32 | 78.1% | 7.84% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Health Services | 23 | 21.7% | 0.28% |
| Producer Manufacturing | 16 | 50.0% | -0.15% |
| Consumer Services | 21 | 33.3% | -1.39% |
| Technology Services | 343 | 44.3% | -4.01% |
| Industrial Services | 24 | 20.8% | -5.07% |
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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 15.45 | -60.0% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 18.48 | -46.4% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 18.48 | -45.7% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 18.48 | -44.8% |
| AEHR | 08-15 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| AEHR | 08-17 | EXTENDED | 99.6 | +36.6% | 145.61 | 81.58 | -44.0% |
| QMCO | 09-29 | EXTENDED | 99.8 | +34.1% | 32.86 | 18.48 | -43.8% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 60.60 | -43.5% |
| RIOT | 09-21 | EXTENDED | 77.9 | +25.8% | 24.18 | 13.72 | -43.3% |
| KEEL | 09-21 | EXTENDED | 63.5 | +23.8% | 4.07 | 2.31 | -43.2% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
