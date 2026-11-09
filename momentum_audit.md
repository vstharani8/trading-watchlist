# Momentum Scan Performance Audit — 2026-11-09

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1078. With forward data: 1078.

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
| EXTENDED | 576 | 37.7% | -3.2% | 37.2% | -5.36% | 30.7% | -8.58% |
| TIGHT | 261 | 45.6% | -0.69% | 40.6% | -3.14% | 39.1% | -2.17% |
| BELOW85 | 146 | 36.3% | -2.23% | 35.6% | -3.64% | 24.7% | -6.63% |
| PULLBACK | 49 | 32.7% | -2.49% | 38.8% | -3.83% | 49.0% | 1.98% |
| EARLY | 46 | 43.5% | -1.28% | 37.0% | -3.53% | 39.1% | -4.17% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 574 | 39.7% | -2.28% | 36.6% | -4.99% | 34.8% | -5.47% |
| <85 | 236 | 33.1% | -3.56% | 36.4% | -4.5% | 23.3% | -8.76% |
| 90-94 | 147 | 45.6% | -1.81% | 43.5% | -3.26% | 44.9% | -3.7% |
| 85-89 | 121 | 43.0% | -0.93% | 39.7% | -3.15% | 29.8% | -6.75% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 81 | 44.4% | -0.5% | 43.2% | -2.24% | 40.7% | -2.5% |
| lifted (0..+5) | 346 | 42.2% | -1.23% | 36.4% | -3.87% | 31.8% | -5.01% |
| extended (>+5) | 576 | 37.7% | -3.2% | 37.2% | -5.36% | 30.7% | -8.58% |
| pullback (-5..-2) | 45 | 35.6% | -1.96% | 44.4% | -1.45% | 46.7% | 0.93% |
| deep-pb (<-5) | 30 | 33.3% | -4.37% | 43.3% | -3.81% | 53.3% | 8.91% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 419 | 35.8% | -2.81% | 36.8% | -4.9% | 31.3% | -8.12% |
| 30-49% | 449 | 41.2% | -2.24% | 35.4% | -4.77% | 28.5% | -7.7% |
| 50+% | 210 | 42.9% | -1.64% | 45.2% | -2.81% | 46.7% | 1.39% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Health Technology | 299 | 57.5% | 6.61% |
| Consumer Services | 8 | 37.5% | 0.07% |
| Energy Minerals | 11 | 54.5% | -0.27% |
| Health Services | 20 | 15.0% | -3.01% |
| Producer Manufacturing | 14 | 42.9% | -4.89% |
| Technology Services | 264 | 39.4% | -6.48% |
| Retail Trade | 10 | 0.0% | -6.53% |
| Industrial Services | 15 | 0.0% | -8.59% |
| Consumer Non-Durables | 11 | 0.0% | -10.1% |
| Non-Energy Minerals | 130 | 9.2% | -12.83% |
| Electronic Technology | 269 | 18.2% | -15.63% |
| Finance | 24 | 8.3% | -18.73% |

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
