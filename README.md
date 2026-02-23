# Trade Policy Shocks and Market Reactions
An Event Study with LLM-Derived Measures of USTR Tariff Announcements

## Overview

This project examines how U.S. trade policy shocks affect equity markets, with a focus on semiconductor-related firms.

Using a standard event study framework, the analysis evaluates market reactions to USTR Section 301 tariff announcements. The study integrates traditional financial econometrics with Large Language Model (LLM)-derived classifications extracted from tariff policy documents.

The objective is to assess whether markets respond more strongly to the severity of policy actions or to the resolution of uncertainty embedded in trade announcements.

---

## Research Question

How do USTR Section 301 tariff announcements impact abnormal returns of semiconductor-related firms, and can LLM-derived policy text measures improve explanatory power in event study regressions?

---

## Data

### Policy Text Data

- USTR Section 301 tariff documents (notices, modifications, exclusions)
- Documents manually selected and parsed into a structured event dataset
- Each event includes:
  - Event date
  - Document type
  - Tariff list
  - Action type
  - Policy direction

### Financial Data

- Daily stock returns for:
  - TSMC
  - Apple
  - NVIDIA
  - AMD
  - Samsung
  - Google
  - Additional semiconductor supply-chain firms
- S&P 500 index used as the market benchmark
- Return data sourced from Yahoo Finance

---

## Methodology

### Event Study Framework

Market model:

Ri,t = αi + βi Rm,t + εi,t

Abnormal returns:

ARi,t = Ri,t − Ři,t

Cumulative abnormal returns:

CARi(t1, t2) = Σ ARi,t

- Estimation window: -120 to -20 trading days
- Event window: -5 to +5 trading days
- Standard errors clustered at the event-date level

---

## LLM Integration

To quantify qualitative trade policy documents, a Large Language Model (Ollama 3.2) was used to classify each announcement according to:

- Severity (0–3 scale)
- Surprise (0–1 scale)
- Direction (tightening, relief, mixed, unknown)
- Rationale (short explanation)

This process transforms unstructured policy text into structured variables suitable for regression analysis.

---

## Regression Specifications

Multiple models were estimated:

1. Manual severity and direction labels
2. LLM-derived severity, surprise, and direction
3. Combined manual + LLM specification
4. Severity index models (TSMC only and all firms)
5. Sector fixed effects specification

Cluster-robust standard errors were applied at the event-date level to account for cross-firm correlation.

---

## Key Findings

- Relief announcements consistently generate positive abnormal returns.
- Markets respond more strongly to information resolution than to severity magnitude.
- Manual direction labels outperform LLM classifications when used independently.
- LLM-derived measures add explanatory value when combined with manual labels.
- Sector-level heterogeneity is observed across firms.

---

## Limitations

- Limited number of tariff events reduces statistical power.
- LLM severity and surprise measures lack formal ground-truth validation.
- Linear regression models may not capture nonlinear policy effects.
- Event dates may not perfectly align with information arrival.

---

## Repository Structure

```
trade-policy-event-study/
│
├── README.md
├── paper.pdf
├── figures/
└── regression_tables/
```

---

## Notes

This repository summarizes an empirical research project integrating event study methodology with AI-based policy text classification. The full paper is included for reference.
