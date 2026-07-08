# voxpop-ai-brand-sentiment
VoxPop: AI-Driven Global Brand Sentiment &amp; Crisis Intelligence Platform
---
Project:-  https://drive.google.com/drive/folders/1GGDjvjTIOEI2-kY8Z4CFntF9eqI6SXNU?usp=sharing
## ✅ Key Results

| Metric | Result | Goal |
|--------|--------|------|
| LSTM F1 Score | **0.8003** | ≥ 0.80 ✅ |
| SGD F1 Score | **0.7786** | Baseline |
| Data Integrity | **100%** | 100% ✅ |
| BART Compression | **6x** | High ✅ |
| BERT Confidence | **0.93-0.98** | High ✅ |
| Chi-Squared p1 | **0.000008** | < 0.05 ✅ |
| Chi-Squared p2 | **0.000075** | < 0.05 ✅ |
| Crisis Rate | **4.4%** | Detected ✅ |

---

## 📋 Tasks Completed

### Task 1 — Data Ingestion & SQL Warehouse
- Downloaded **Sentiment140 dataset** (1.6M tweets) from HuggingFace
- Built **TextCleaner** class using Regex for noise removal
- Built **DimensionEnricher** for synthetic metadata generation
- Built **JSONPayloadProcessor** using map/filter operations
- Designed **SQLite Star Schema** with 5 tables:
  - `Fact_Reviews` (central fact table)
  - `Dim_Users`, `Dim_Location`, `Dim_Sentiment`, `Dim_Platform`
- Implemented **ACID transactions** (BEGIN/COMMIT/ROLLBACK)
- Achieved **100% Data Integrity Score**
- Exported `voxpop.db` + `voxpop_clean_data.csv`

### Task 2 — Classical ML & EDA
- Sampled **100,000 real tweets** with actual Sentiment140 labels
- Applied **advanced text cleaning** (contraction expansion, regex)
- Built **TF-IDF Vectorizer** (50,000 features + trigrams)
- Trained **3 Classical ML Models**:
  - Logistic Regression → F1: **0.7523**
  - LinearSVC → F1: **0.7557**
  - SGD Classifier → F1: **0.7786** (Best!)
- Performed **K-Means Clustering** → 5 business topics:
  - Product Quality, App & Tech Issues, Customer Service
  - Pricing & Value, Shipping & Delivery
- Generated **EDA visualizations** (pie charts, heatmaps, word clouds)

### Task 3 — Deep Learning BiLSTM
- Built custom **Vocabulary** class (20,000 words)
- Built custom **PyTorch Dataset + DataLoader**
- Designed **Bidirectional LSTM** architecture:
  - Embedding: 256 dimensions
  - BiLSTM: 2 layers, 512 hidden units
  - Dropout: 0.4 (prevents overfitting)
  - Output: Sigmoid activation
- Training techniques:
  - BCELoss + Adam optimizer
  - Learning Rate Scheduler
  - Gradient Clipping (max_norm=1.0)
  - Early Stopping (best model saved)
- Fine-tuned for 5 additional epochs
- **Final F1 Score: 0.8003 ≥ 0.80** ✅
- Built **Anger Score detector** (0=calm, 1=crisis)

### Task 4 — Generative AI & NLP
- **BART Summarization** (facebook/bart-large-cnn):
  - Condensed 1000 reviews → 3 sentences
  - **6x compression ratio**
- **BERT Sentiment Analysis** (cardiffnlp/twitter-roberta-base-sentiment):
  - Confidence scores: **0.93-0.98**
- **BERT NER** (dslim/bert-base-NER):
  - Extracted **13 named entities**
  - ORG: Microsoft Teams, Netflix, Nike
  - MISC: Apple iPhone 15, Windows 11
  - PER: Elon Musk | LOC: Amazon
- **Brand Assistant Chatbot** (5 query types):
  - Top complaints, Overall sentiment
  - Crisis alerts, Topic distribution
  - Positive highlights

### Task 5 — Statistics & Dashboard
- **Chi-Squared Hypothesis Testing**:
  - Test 1: Sentiment vs Crisis → p=0.000008 ✅
  - Test 2: Topic vs Crisis → p=0.000075 ✅
- **NSS Score**: 0.1% | **Crisis Rate**: 4.4%
- **Streamlit Dashboard** deployed on HuggingFace:
  - Interactive filters (Sentiment, Topic, Crisis)
  - 4 analytical charts
  - Interactive Word Cloud
  - GenAI Cards (BART + BERT + NER)
  - Brand Assistant Chatbot
  - **Live Sentiment Predictor** ← Most powerful feature!
  - BERT Confidence Score chart
  - Sample Reviews with color coding

---

## 🚀 Live Features

### 🔮 Live Sentiment Predictor
Type any review and instantly get:
- ✅ Sentiment (Positive/Negative/Neutral)
- 📊 Confidence Score (0 to 1)
- 😡 Anger Score (0 to 1)
- 🚨 Alert Status (NORMAL / HIGH RISK / CRISIS)

### 💬 Brand Assistant
Ask questions in plain English:
- *"What are the top complaints?"*
- *"What is the overall sentiment?"*
- *"Are there any crisis alerts?"*
- *"What are the main topics?"*
- *"What are the positive highlights?"*

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|-----------|
| Language | Python 3.10 |
| Database | SQLite |
| Data Processing | Pandas, NumPy |
| Classical ML | Scikit-Learn |
| Deep Learning | PyTorch |
| NLP Models | HuggingFace Transformers |
| Summarization | BART (facebook/bart-large-cnn) |
| Sentiment | RoBERTa (cardiffnlp) |
| NER | BERT (dslim/bert-base-NER) |
| Visualization | Matplotlib, WordCloud |
| Dashboard | Streamlit |
| Deployment | HuggingFace Spaces |
| Statistics | SciPy |
| Synthetic Data | Faker |

---

## 📁 Project Structure
