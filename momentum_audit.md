# Momentum Scan Performance Audit — 2026-10-23

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1337. With forward data: 1337.

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
| EXTENDED | 762 | 41.9% | -1.16% | 42.7% | -3.29% | 32.5% | -6.58% |
| TIGHT | 297 | 49.2% | 0.09% | 45.1% | -1.23% | 41.4% | -0.31% |
| BELOW85 | 171 | 41.5% | -1.15% | 43.3% | -1.44% | 32.7% | -3.74% |
| PULLBACK | 57 | 40.4% | -1.07% | 47.4% | -2.35% | 56.1% | 4.08% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.88% | 40.0% | -5.19% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 709 | 44.8% | -0.65% | 40.7% | -3.24% | 35.2% | -4.1% |
| <85 | 292 | 40.4% | -1.22% | 45.5% | -1.79% | 33.6% | -5.09% |
| 90-94 | 186 | 44.1% | -1.43% | 49.5% | -1.45% | 46.2% | -2.5% |
| 85-89 | 150 | 43.3% | -0.47% | 44.0% | -2.03% | 30.0% | -5.92% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 96 | 47.9% | 0.3% | 47.9% | -0.31% | 44.8% | 0.0% |
| lifted (0..+5) | 392 | 46.4% | -0.43% | 41.6% | -2.09% | 35.7% | -3.22% |
| extended (>+5) | 762 | 41.9% | -1.16% | 42.7% | -3.29% | 32.5% | -6.58% |
| pullback (-5..-2) | 50 | 42.0% | -0.58% | 50.0% | 0.4% | 50.0% | 2.29% |
| deep-pb (<-5) | 37 | 37.8% | -2.91% | 54.1% | -1.65% | 62.2% | 10.56% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 567 | 42.7% | -0.75% | 44.8% | -1.95% | 37.6% | -4.85% |
| 30-49% | 532 | 44.0% | -0.98% | 40.4% | -3.13% | 30.8% | -6.08% |
| 50+% | 238 | 44.8% | -0.89% | 46.5% | -2.61% | 43.0% | 1.17% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 14 | 78.6% | 9.35% |
| Health Technology | 364 | 55.9% | 7.56% |
| Energy Minerals | 30 | 76.7% | 7.33% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | -0.95% |
| Consumer Services | 21 | 33.3% | -1.36% |
| Health Services | 21 | 14.3% | -3.85% |
| Technology Services | 333 | 43.2% | -4.37% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Industrial Services | 21 | 19.0% | -8.19% |
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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 15.46 | -60.0% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 16.98 | -50.8% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 16.98 | -50.1% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 16.98 | -49.3% |
| QMCO | 09-29 | EXTENDED | 99.8 | +34.1% | 32.86 | 16.98 | -48.3% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 55.65 | -48.1% |
| QMCO | 10-01 | EXTENDED | 99.8 | +44.4% | 31.89 | 16.98 | -46.8% |
| AEHR | 10-05 | EXTENDED | 98.8 | +37.3% | 104.40 | 55.65 | -46.7% |
| QMCO | 09-30 | EXTENDED | 99.8 | +40.3% | 31.72 | 16.98 | -46.5% |
| QMCO | 09-28 | EXTENDED | 99.8 | +42.0% | 31.40 | 16.98 | -45.9% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
