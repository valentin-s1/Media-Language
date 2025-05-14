# Exploratory Project – Media Framing and Public Preferences in Swiss Referenda

## Project Overview

This exploratory project investigates whether media coverage in Switzerland reflects public sentiment ahead of direct democratic referenda. We analyze whether the **tone, vocabulary, and topical framing** of news articles can serve as a proxy for political preferences, **without claiming causal influence**.

We collected 113 articles covering 20 national referenda (2011–2024) from **SRF**, **20 Minuten**, and **NZZ**, each published prior to the vote. Using a mix of NLP techniques and pre-trained language models, we examine whether patterns in text data align with final vote outcomes.

The project is structured into three main steps:

### 1. Data Retrieval & Preprocessing
- Articles retrieved manually and via basic scraping tools
- Text cleaning: removal of non-content elements, words and phrases
- NLP preprocessing: tokenization, stopword removal, compound splitting, lemmatization, etc.

### 2. Descriptive Analysis
- Distribution of articles across media outlets and referenda
- Word clouds by outcome (accepted vs. rejected)
- Zero-shot topic classification using a multilingual BART model

### 3. Modelling & Interpretation
- **Sentiment analysis** shows most media texts are neutral (~85%), limiting predictive power
- **Stance detection** (manual labeling + classifier) was hindered by class imbalance and limited sample size
- **Logistic regression** on textual features failed to predict outcomes reliably, suggesting either true neutrality of coverage or methodological limitations

While results suggest **media framing is largely neutral**, interpretation must remain cautious due to sample size, model constraints, and pre-trained model transferability.

---

## Repository:

This repository contains the full analysis for the Media-Language project. The main workflow is documented in the Jupyter Notebook:

- `/Jupyter_COde.ipynb`

---

## How to Run

1. **Clone the repository**  
```bash
git clone https://github.com/valentin-s1/Media-Language.git
cd Media-Language
```

3. Create and activate a conda enfironement
```bash
conda create -n media-nlp python=3.10
conda activate media-nlp
```
3. Install required packages
Start by running Jupyter Notebook (install required packages in beginning of Notebook)

## Repository Content
- [`Jupyter_Code.ipynb`](./Jupyter_Code.ipynb)
  → Main Jupyter Notebook containing the full analysis pipeline.

- [`Data_ML.xlsx`](./Data_ML.xlsx)
  → Original dataset including article URLs.

- [`Data_ML_filled.xlsx`](./Data_ML_filled.xlsx)
  → Scraped data without cleaning (raw text data).

- [`Data_ML_cleaned.xlsx`](./Data_ML_cleaned.xlsx)
  → Preprocessed and cleaned text data (after NLP pipeline).

- [`stance_sample.xlsx`](./stance_sample.xlsx)
  → Randomly selected sample used for stance detection.

- [`stance_sample_labeled.xlsx`](./stance_sample_labeled.xlsx)
  → Manually labeled version of the stance detection sample.

- [`.gitignore`](./.gitignore)
  → Specifies files/folders (e.g., large stance data) that should be excluded from version control.

- [`Presentation/Media-Language.pptx`](./Presentation/Media-Language.pptx)
  → PowerPoint presentation summarizing the project and results.

