# 📊 Social Media Sentiment & Engagement Tracker

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python) ![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow?logo=powerbi) ![NLP](https://img.shields.io/badge/NLP-VADER%20%7C%20TextBlob-green) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

An end-to-end NLP and business intelligence project analyzing sentiment patterns across 61,949 tweets covering 20+ major brands and gaming titles. The project applies VADER and TextBlob sentiment classification, compares model performance against human-annotated labels, and delivers insights through an interactive Power BI dashboard.

---

## 📊 Dashboard Preview

> Built in Power BI — 4 interactive charts covering sentiment distribution, brand-level sentiment, average sentiment scores, and tweet length patterns.

---

## 🎯 Project Objectives

- Classify 61,949 tweets into Positive, Negative, and Neutral sentiment using VADER and TextBlob
- Compare NLP model performance against human-annotated ground truth labels
- Identify most positive and most negative brands from social media discourse
- Deliver actionable engagement insights through a Power BI dashboard

---

## 📁 Project Structure

```
social-media-sentiment-tracker/
│
├── data/
│   ├── raw/
│   │   ├── twitter_training.csv          ← original training data (74,682 tweets)
│   │   └── twitter_validation.csv        ← original validation data (1,000 tweets)
│   └── processed/
│       ├── sentiment_analysis_final.csv  ← cleaned + scored dataset
│       └── text_length_summary.csv       ← aggregated summary for Power BI
│
├── notebooks/
│   └── 01_sentiment_analysis.ipynb       ← full analysis notebook
│
├── visuals/
│   ├── sentiment_distribution_comparison.png
│   ├── sentiment_by_entity.png
│   ├── vader_score_distribution.png
│   └── brand_vader_scores.png
│
├── dashboard/
│   └── Social_Media_Sentiment_Dashboard.pbix
│
└── README.md
```

---

## 🗃️ Dataset

| Property | Details |
|---|---|
| Source | [Kaggle — Twitter Entity Sentiment Analysis](https://www.kaggle.com/datasets/jp797498e/twitter-entity-sentiment-analysis) |
| Training records | 74,682 tweets |
| Validation records | 1,000 tweets |
| Total after cleaning | 61,949 tweets |
| Sentiment labels | Positive, Negative, Neutral, Irrelevant |
| Entities covered | 20+ brands including Amazon, Microsoft, NBA2K, MaddenNFL, Nvidia, Facebook |

---

## 🔧 Tools & Technologies

| Category | Tools |
|---|---|
| Language | Python 3.11 |
| Data Manipulation | pandas, numpy |
| NLP Libraries | VADER (vaderSentiment), TextBlob |
| Visualization | matplotlib, seaborn |
| BI Dashboard | Power BI Desktop |
| Environment | VS Code |

---

## 🧹 Data Cleaning

- Combined training (74,682) and validation (1,000) datasets
- Dropped 686 rows with missing tweet text
- Removed 13,162 tweets labelled "Irrelevant" — not relevant to brand sentiment
- Applied text cleaning pipeline: lowercasing, URL removal, mention removal, hashtag removal, punctuation stripping
- Final clean dataset: **61,949 tweets** across 3 sentiment classes

---

## 🤖 Sentiment Analysis

### VADER (Valence Aware Dictionary and sEntiment Reasoner)
- Lexicon-based model designed for social media text
- Compound score range: -1.0 (most negative) to +1.0 (most positive)
- Thresholds: ≥ 0.05 = Positive, ≤ -0.05 = Negative, else Neutral

### TextBlob
- Pattern-based NLP library using polarity scores
- Polarity range: -1.0 to +1.0
- Thresholds: > 0 = Positive, < 0 = Negative, = 0 = Neutral

### Model Accuracy vs Human Labels

| Model | Accuracy |
|---|---|
| VADER | 49.77% |
| TextBlob | 48.26% |

> **Important context:** The ~50% accuracy reflects a domain mismatch — both models are trained on general English text, while this dataset contains gaming-specific language where phrases like "I will destroy you" carry positive connotations. This is a well-documented challenge in domain-specific NLP and motivated the use of engagement pattern analysis alongside lexical sentiment scoring.

---

## 📈 Key Findings

### Sentiment Distribution
- **Negative: 36.17%** — social media skews negative; users complain more than praise
- **Positive: 32.74%** — strong positive communities around gaming titles
- **Neutral: 29.49%** — factual/informational tweets

### Most Positive Brands (Avg VADER Score)
| Brand | Avg VADER Score |
|---|---|
| Amazon | +0.271 |
| AssassinsCreed | +0.229 |
| Hearthstone | +0.220 |
| Borderlands | +0.205 |
| WorldOfCraft | +0.188 |

### Most Negative Brands (Avg VADER Score)
| Brand | Avg VADER Score |
|---|---|
| RedDeadRedemption | -0.261 |
| Facebook | -0.190 |
| johnson&johnson | -0.120 |
| NBA2K | -0.115 |
| MaddenNFL | -0.085 |

### Tweet Length by Sentiment
- Neutral tweets are longest (~115 chars) — users explain neutral opinions in more detail
- Negative tweets are slightly longer (~120 chars) — users elaborate when venting
- Positive tweets are shortest (~95 chars) — positive reactions tend to be brief

---

## 📊 Power BI Dashboard

The interactive dashboard contains 4 views:

1. **Sentiment Distribution** — Donut chart showing overall Positive/Negative/Neutral breakdown
2. **Top 10 Brands by Sentiment** — Stacked bar chart comparing sentiment mix across brands
3. **Average Sentiment Score by Brand** — Horizontal bar showing most positive vs most negative brands
4. **Average Tweet Length by Sentiment** — Column chart revealing engagement depth by sentiment type

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/social-media-sentiment-tracker.git
cd social-media-sentiment-tracker
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn vaderSentiment textblob
```

**3. Download the dataset**
- Download from [Kaggle](https://www.kaggle.com/datasets/jp797498e/twitter-entity-sentiment-analysis)
- Place `twitter_training.csv` and `twitter_validation.csv` in `data/raw/`

**4. Run the notebook**
```bash
jupyter notebook notebooks/01_sentiment_analysis.ipynb
```

**5. View the dashboard**
- Open `dashboard/Social_Media_Sentiment_Dashboard.pbix` in Power BI Desktop
- Or view the published version on Power BI Service *(link here)*

---

## 💡 Business Recommendations

1. **MaddenNFL & NBA2K need community management attention** — both show heavily negative sentiment, likely driven by gameplay bugs and matchmaking complaints
2. **Amazon's positive sentiment is a competitive advantage** — leverage user satisfaction in marketing campaigns
3. **Facebook's negative sentiment reflects real reputation risk** — privacy and misinformation concerns dominate discourse
4. **Negative tweets are longer** — brands should prioritise responding to longer tweets as they contain more detailed complaints worth addressing
5. **Gaming brands should use domain-trained NLP models** — general-purpose models like VADER underperform on gaming slang; fine-tuned models would improve classification accuracy

---

## 👤 Author

**Mohammad Ammar Ahsan**
B.E. in Artificial Intelligence & Data Science
Muffakham Jah College of Engineering and Technology, Hyderabad

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://linkedin.com/in/ammar-ahsan-850205201)
📧 ammarahsanmaa786@gmail.com | 📞 +91 94902 11907

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
