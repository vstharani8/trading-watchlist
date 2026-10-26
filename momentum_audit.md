# Momentum Scan Performance Audit — 2026-10-26

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1300. With forward data: 1300.

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
| EXTENDED | 755 | 41.6% | -1.21% | 42.2% | -3.42% | 32.1% | -6.55% |
| TIGHT | 281 | 47.7% | -0.14% | 43.4% | -2.08% | 39.9% | -0.93% |
| BELOW85 | 159 | 39.6% | -1.51% | 39.0% | -2.71% | 28.9% | -5.04% |
| PULLBACK | 55 | 38.2% | -1.24% | 45.5% | -2.5% | 54.5% | 2.92% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.88% | 40.0% | -5.08% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 692 | 44.1% | -0.74% | 39.9% | -3.55% | 34.3% | -4.42% |
| <85 | 279 | 39.1% | -1.47% | 43.0% | -2.61% | 31.2% | -6.0% |
| 90-94 | 179 | 42.5% | -1.73% | 47.5% | -2.16% | 44.7% | -2.72% |
| 85-89 | 150 | 43.3% | -0.47% | 44.0% | -2.03% | 30.7% | -5.78% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 87 | 47.1% | -0.1% | 47.1% | -1.26% | 43.7% | -1.06% |
| lifted (0..+5) | 377 | 44.8% | -0.59% | 39.3% | -2.81% | 34.0% | -3.76% |
| extended (>+5) | 755 | 41.6% | -1.21% | 42.2% | -3.42% | 32.1% | -6.55% |
| pullback (-5..-2) | 48 | 39.6% | -1.16% | 47.9% | -1.04% | 47.9% | 1.16% |
| deep-pb (<-5) | 33 | 36.4% | -3.32% | 48.5% | -2.41% | 57.6% | 9.06% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 543 | 41.6% | -0.95% | 43.1% | -2.63% | 36.1% | -5.53% |
| 30-49% | 524 | 43.1% | -1.06% | 39.5% | -3.44% | 29.8% | -6.38% |
| 50+% | 233 | 44.2% | -1.0% | 45.6% | -2.77% | 42.5% | 1.28% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 10 | 70.0% | 7.65% |
| Health Technology | 348 | 55.4% | 7.36% |
| Energy Minerals | 27 | 74.1% | 6.96% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | -0.91% |
| Consumer Services | 21 | 33.3% | -1.41% |
| Health Services | 21 | 14.3% | -3.74% |
| Technology Services | 321 | 41.7% | -4.74% |
| Retail Trade | 13 | 0.0% | -6.44% |
| Consumer Non-Durables | 13 | 0.0% | -9.47% |
| Industrial Services | 19 | 10.5% | -10.26% |
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
| XRPN | 10-05 | EXTENDED | 99.7 | +274.7% | 38.65 | 15.06 | -61.0% |
| QMCO | 10-02 | EXTENDED | 99.8 | +33.7% | 34.50 | 17.62 | -48.9% |
| AEHR | 10-02 | TIGHT | 98.9 | +30.4% | 107.21 | 55.31 | -48.4% |
| QMCO | 10-05 | EXTENDED | 99.8 | +43.5% | 34.01 | 17.62 | -48.2% |
| QMCO | 10-06 | EXTENDED | 99.7 | +39.0% | 33.47 | 17.62 | -47.4% |
| AEHR | 10-05 | EXTENDED | 98.8 | +37.3% | 104.40 | 55.31 | -47.0% |
| QMCO | 09-29 | EXTENDED | 99.8 | +34.1% | 32.86 | 17.62 | -46.4% |
| FCEL | 10-06 | EXTENDED | 95.1 | +24.4% | 20.65 | 11.11 | -46.2% |
| AEHR | 10-01 | TIGHT | 98.7 | +22.5% | 101.60 | 55.31 | -45.6% |
| RIOT | 09-24 | EXTENDED | 83.7 | +23.3% | 23.48 | 12.89 | -45.1% |

## Suggested Rules (placeholder — finalize after reading the data)

- [FILL: which setup proxy to prioritize]
- [FILL: RS threshold]
- [FILL: dist10 zone preference]
- [FILL: 1M momentum threshold]
