Trade Policy Shocks and Market Reactions

An Event Study with LLM-Derived Measures of USTR Tariff Announcements

Overview

This project examines how U.S. trade policy shocks affect equity markets, with a focus on semiconductor-related firms.

Using a standard event study framework, we analyze market reactions to USTR Section 301 tariff announcements. The study integrates traditional financial econometrics with Large Language Model (LLM)-derived classifications extracted from tariff policy documents.

The objective is to evaluate whether markets respond more strongly to the severity of policy actions or to the resolution of uncertainty embedded in trade announcements.

Research Question

How do USTR Section 301 tariff announcements impact abnormal returns of semiconductor-related firms, and can LLM-derived policy text measures improve explanatory power in event study regressions?

Data
Policy Text Data

USTR Section 301 tariff documents (notices, modifications, exclusions)

Documents manually selected and parsed into structured event dataset

Each event includes:

Event date

Document type

Tariff list

Action type

Policy direction

Financial Data

Daily stock returns for:

TSMC

Apple

NVIDIA

AMD

Samsung

Google

Supply-chain related firms

S&P 500 index used as market benchmark

Data sourced via Yahoo Finance

Methodology
Event Study Framework

We implement a standard market model:

Ri,t = αi + βi Rm,t + εi,t

Abnormal returns:

ARi,t = Ri,t − Ři,t

Cumulative abnormal returns:

CARi(t1, t2) = Σ ARi,t

Estimation window: -120 to -20 days

Event window: -5 to +5 days

Standard errors clustered at the event-date level

LLM Integration

To quantify qualitative trade policy documents, we use a Large Language Model (Ollama 3.2) to classify each announcement according to:

Severity (0–3 scale)

Surprise (0–1 scale)

Direction (tightening, relief, mixed, unknown)

Rationale (brief explanation)

The LLM transforms unstructured policy text into structured regression variables.

Regression Specifications

We estimate multiple models:

Manual severity and direction labels

LLM-derived severity, surprise, and direction

Combined manual + LLM model

Severity index models (TSMC only and all firms)

Sector fixed effects specification

Cluster-robust standard errors are applied at the event-date level.

Key Findings

Relief announcements consistently generate positive abnormal returns.

Markets respond more strongly to information resolution than to severity magnitude.

Manual direction labels outperform LLM classifications when used independently.

LLM-derived measures add explanatory value when combined with manual labels.

Sector-level heterogeneity is present across firms.

Limitations

Limited number of tariff events reduces statistical power.

LLM severity and surprise lack ground truth validation.

Linear regression framework may not capture nonlinear policy effects.

Event timing may not perfectly align with information arrival.

Figures

Selected figures and regression output summaries are included in this repository.

Repository Structure

trade-policy-event-study/
│
├── README.md
├── paper.pdf
├── figures/
└── regression_tables/
