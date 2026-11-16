# Momentum Scan Performance Audit — 2026-11-16

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 846. With forward data: 846.

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
| EXTENDED | 401 | 38.9% | -2.64% | 34.9% | -5.39% | 32.4% | -8.15% |
| TIGHT | 233 | 45.1% | -0.83% | 38.2% | -3.53% | 38.2% | -2.67% |
| BELOW85 | 125 | 37.6% | -1.98% | 36.0% | -3.52% | 25.6% | -6.88% |
| PULLBACK | 48 | 31.2% | -2.78% | 37.5% | -4.08% | 47.9% | 1.78% |
| EARLY | 39 | 41.0% | -1.12% | 33.3% | -3.27% | 35.9% | -3.58% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 459 | 41.8% | -1.65% | 38.3% | -4.26% | 36.8% | -4.74% |
| <85 | 194 | 34.0% | -3.16% | 36.1% | -4.35% | 25.8% | -8.36% |
| 90-94 | 105 | 46.7% | -1.32% | 36.2% | -4.25% | 41.9% | -3.5% |
| 85-89 | 88 | 36.4% | -1.92% | 23.9% | -5.73% | 28.4% | -7.29% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 71 | 46.5% | -0.61% | 42.3% | -2.46% | 40.8% | -2.6% |
| lifted (0..+5) | 300 | 41.7% | -1.15% | 34.3% | -4.08% | 31.0% | -5.5% |
| extended (>+5) | 401 | 38.9% | -2.64% | 34.9% | -5.39% | 32.4% | -8.15% |
| pullback (-5..-2) | 44 | 34.1% | -2.26% | 43.2% | -1.68% | 45.5% | 0.68% |
| deep-pb (<-5) | 30 | 33.3% | -4.37% | 43.3% | -3.81% | 53.3% | 8.91% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 330 | 35.5% | -2.7% | 35.5% | -5.16% | 31.2% | -8.68% |
| 30-49% | 350 | 43.4% | -1.54% | 34.3% | -4.4% | 28.3% | -7.32% |
| 50+% | 166 | 42.2% | -1.49% | 41.0% | -3.04% | 51.8% | 3.71% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 260 | 57.3% | 6.45% |
| Health Services | 16 | 18.8% | -2.02% |
| Energy Minerals | 7 | 42.9% | -2.51% |
| Consumer Services | 2 | 0.0% | -3.52% |
| Producer Manufacturing | 9 | 55.6% | -4.06% |
| Retail Trade | 10 | 0.0% | -6.53% |
| Technology Services | 199 | 37.7% | -7.12% |
| Industrial Services | 10 | 0.0% | -8.9% |
| Process Industries | 1 | 0.0% | -12.28% |
| Consumer Non-Durables | 5 | 0.0% | -12.52% |
| Electronic Technology | 197 | 22.3% | -14.1% |
| Non-Energy Minerals | 107 | 6.5% | -14.22% |

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
