# Media-Language
Media Language and Direct Democracy: Can News Articles Reflect the Political Climate?

## Project Summary

This project investigates whether the language used in Swiss media articles reflects the general *political climate* around national referenda. Specifically, we examine whether the textual content of news articles published in the weeks before a referendum can be used to predict the final outcome of the vote (acceptance vs. rejection).

Importantly, this project **does not aim to test whether media coverage causes certain outcomes**, nor whether media influence individual opinions. Instead, our goal is to evaluate whether **machine learning algorithms** and **text analysis** techniques can detect signals in media coverage that correlate with societal sentiment toward specific referenda.

We apply Natural Language Processing (NLP) techniques and supervised machine learning models to classify referenda outcomes based solely on the textual features of articles published in the pre-vote period.

---

## Research Question

**Can the textual content of media articles be used to predict whether a Swiss referendum will be accepted or rejected?**  
More specifically:  
> *Do news articles published before a national vote reflect the underlying political climate well enough to allow for predictive classification of the outcome?*

---

## Project Structure & Approach

The project follows the typical data science pipeline:

### 1. Data Retrieval & Management

- We manually collected a sample of ~80–100 news articles covering ~20–30 Swiss referenda (from 2000–2024), drawn from sources without paywalls such as **SRF**, **Watson**, and **20 Minuten**.
- Metadata such as referendum title, article URL, source, publication date, and outcome (1 = accepted, 0 = rejected) are stored in a structured `.csv` file.
- The textual content was scraped automatically using Python scripts (e.g. BeautifulSoup), where allowed.
- Texts were cleaned (e.g. lowercased, stopwords removed, lemmatized) for analysis.

### 2. Descriptive Analysis & Visualization

- We compute basic statistics on the distribution of vote outcomes, article sources, average article length, and vocabulary.
- Sentiment distributions are visualized across accepted/rejected referenda.
- We explore word frequencies and keyword clouds by class.

### 3. Modelling (NLP & ML)

We pursue **two modelling paths**:

- **Approach A**: Use vectorized article texts (TF-IDF) to train supervised classifiers (e.g. logistic regression, random forest) to predict the referendum outcome.
- **Approach B**: Compute sentiment scores using off-the-shelf sentiment analysis tools (e.g. VADER) and examine whether aggregated sentiment predicts acceptance.

Both models are evaluated using standard metrics (accuracy, precision, recall, confusion matrix) and cross-validation.

---

## Key Limitations & Clarifications

We emphasize that:

- **No causal claims** are made. We do not test whether media content influences voting behavior, but only whether it captures relevant information about the *collective mood*.
- Articles often contain **mixed sentiment** (e.g. criticizing the government, not the initiative). Sentiment scores may reflect general tone, not the stance on the issue itself.
- **Topic bias** may exist: Some policy domains (e.g. immigration, environment) may correlate with typical outcomes regardless of wording.
- Media articles do not represent all voters’ views, especially in polarized or low-turnout votes.
- Our dataset is relatively small, which limits the generalizability of the models.

---

## How to Use This Repository

### 📁 Folder Structure


## 🛠️ Environment & Installation

This project requires a working Python environment.  
We recommend using [Anaconda](https://www.anaconda.com/) to manage environments.

### 💻 Recommended Environment Setup

Create a conda environment with compatible versions:

```bash
conda create -n media-nlp python=3.10
conda activate media-nlp
conda install pandas numpy=1.24 spacy wordcloud matplotlib seaborn scikit-learn
python -m spacy download de_core_news_sm