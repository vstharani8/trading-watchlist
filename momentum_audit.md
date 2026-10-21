# Momentum Scan Performance Audit — 2026-10-21

Lookback: 90 calendar days. Forward windows: [5, 10, 20] trading days.
Total scan appearances: 1361. With forward data: 1361.

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
| EXTENDED | 766 | 42.0% | -1.17% | 42.9% | -3.2% | 33.7% | -5.49% |
| TIGHT | 307 | 49.8% | 0.22% | 45.9% | -0.89% | 43.0% | 0.52% |
| BELOW85 | 177 | 42.4% | -0.99% | 45.2% | -0.84% | 34.5% | -2.88% |
| PULLBACK | 61 | 42.6% | -0.91% | 50.8% | -1.49% | 59.0% | 6.11% |
| EARLY | 50 | 46.0% | -0.94% | 38.0% | -2.88% | 40.0% | -4.17% |

## Performance by RS Bucket

| RS | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 95+ | 720 | 45.1% | -0.6% | 41.2% | -3.07% | 37.1% | -2.62% |
| <85 | 298 | 40.9% | -1.13% | 46.6% | -1.42% | 34.6% | -4.44% |
| 90-94 | 192 | 45.0% | -1.4% | 50.8% | -0.93% | 47.6% | -1.62% |
| 85-89 | 151 | 43.7% | -0.43% | 44.4% | -1.92% | 30.5% | -5.58% |

## Performance by dist10 Bucket

| dist10 zone | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| tight (-2..0) | 100 | 48.0% | 0.37% | 48.0% | 0.01% | 46.0% | 0.56% |
| lifted (0..+5) | 402 | 47.3% | -0.32% | 42.8% | -1.74% | 37.1% | -2.31% |
| extended (>+5) | 766 | 42.0% | -1.17% | 42.9% | -3.2% | 33.7% | -5.49% |
| pullback (-5..-2) | 53 | 43.4% | -0.39% | 52.8% | 1.42% | 52.8% | 3.71% |
| deep-pb (<-5) | 40 | 40.0% | -2.48% | 57.5% | -0.79% | 65.0% | 12.31% |

## Performance by 1M Momentum Bucket

| 1M% | N | 5d Win% | 5d Avg% | 10d Win% | 10d Avg% | 20d Win% | 20d Avg% |
|---|---:|---:|---:|---:|---:|---:|---:|
| 20-29% | 581 | 43.2% | -0.67% | 45.8% | -1.55% | 38.9% | -3.56% |
| 30-49% | 538 | 44.2% | -0.98% | 40.9% | -2.96% | 31.8% | -5.08% |
| 50+% | 242 | 45.5% | -0.76% | 47.2% | -2.5% | 45.9% | 1.97% |

## Top 12 Sectors (by 20d avg)

| Sector | N | 20d Win% | 20d Avg% |
|---|---:|---:|---:|
| Commercial Services | 16 | 81.2% | 10.7% |
| Health Technology | 376 | 58.6% | 8.98% |
| Energy Minerals | 32 | 78.1% | 7.84% |
| Consumer Durables | 1 | 100.0% | 0.38% |
| Producer Manufacturing | 16 | 50.0% | -0.16% |
| Health Services | 22 | 18.2% | -1.07% |
| Consumer Services | 21 | 33.3% | -1.13% |
| Technology Services | 338 | 44.1% | -3.97% |
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
| IOVA | 07-24 | EXTENDED | 91.4 | +28.2% | 4.99 | 8.29 | +66.1% |
| IOVA | 09-02 | TIGHT | 98.8 | +86.9% | 8.62 | 14.23 | +65.1% |
| IOVA | 09-10 | TIGHT | 98.8 | +33.6% | 8.14 | 13.31 | +63.5% |
| IOVA | 09-03 | EXTENDED | 98.8 | +110.2% | 8.70 | 14.22 | +63.5% |
| IOVA | 09-04 | EXTENDED | 98.7 | +98.2% | 8.79 | 14.15 | +61.0% |
| AMLX | 08-05 | EXTENDED | 94.9 | +20.7% | 21.85 | 34.49 | +57.9% |
| IOVA | 09-14 | TIGHT | 99.0 | +32.5% | 9.26 | 14.56 | +57.2% |

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
