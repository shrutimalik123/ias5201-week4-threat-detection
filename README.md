# Week 4: AI-Based Threat Detection in Social Media

**Course:** IAS5201 – AI in Cybersecurity  
**Institution:** Capella University  
**Instructor:** Professor Stuart McCubbrey  
**Author:** Shruti Malik  

---

## Overview

This repository contains the Week 4 assignment for IAS5201. The project demonstrates how natural language processing (NLP) can be applied to social media data to identify potential cybersecurity threats.

## Files

| File | Description |
|------|-------------|
| `cf_week_4_assignment_code.docx` | Original assignment code document provided by the course |
| `Week4_Assignment_ShrMalik.docx` | 500-word reflection paper (APA 7th edition) |

## What the Code Does

The Python pipeline (run in Google Colab) processes 110 simulated cybersecurity tweets through five stages:

1. **Text Cleaning** – strips URLs, usernames, hashtags, and special characters
2. **Keyword Detection** – flags posts containing terms like `exploit`, `malware`, `vulnerability`, `cve`, `zero-day`, `sql injection`, `rce`
3. **Named Entity Recognition** – uses spaCy (`en_core_web_sm`) to extract technical and organizational entities
4. **Sentiment Analysis** – uses TextBlob to score each post's polarity (−1.0 to +1.0)
5. **Threat Alert Generation** – elevates a post to high-risk when it matches a keyword **and** has sentiment polarity below −0.2

## Results Summary

| Metric | Value |
|--------|-------|
| Total tweets analyzed | 110 |
| Keyword matches | 59 (53.6%) |
| Negative sentiment tweets (< −0.2) | 2 |
| High-risk alerts generated | 2 |
| Mean sentiment score | +0.103 |

## Dependencies

```
spacy>=3.8
textblob>=0.20
gdown>=6.5
pandas
matplotlib
```

Install and run in [Google Colab](https://colab.research.google.com/) by pasting the code from `cf_week_4_assignment_code.docx`.

## Key Concepts Covered

- NLP for cybersecurity threat intelligence
- Keyword-based rule systems vs. machine learning classifiers
- Sentiment analysis as a secondary signal for threat severity
- Challenges of imbalanced datasets in security contexts
- Potential improvements: transformer models (BERT/SecBERT), SMOTE for class imbalance, supervised classification

## References

See `Week4_Assignment_ShrMalik.docx` for full APA citations, including:

- Apruzzese et al. (2023) — adversarial attacks on ML security systems
- Chawla et al. (2002) — SMOTE for class imbalance
- Ranade et al. (2021) — NLP on cyber threat intelligence
- Siddiqui et al. (2021) — ML for cybersecurity threat analysis
- Anthropic (2026) — Claude (claude-sonnet-4-6) [Large language model]
