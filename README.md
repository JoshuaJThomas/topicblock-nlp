# TopicBlock — NLP Topic Modelling

Research project building a topic modelling pipeline to extract latent themes from large document corpora using LDA and NMF.

## Overview
Applies Latent Dirichlet Allocation (LDA) and Non-negative Matrix Factorisation (NMF) to AI research literature. Evaluates coherence scores across topic counts and surfaces dominant themes per document cluster.

## Tech Stack
- Python 3.x
- NLTK / spaCy
- Gensim (LDA)
- Scikit-learn (NMF)
- Pandas / NumPy
- Matplotlib / WordCloud

## Structure
```
notebooks/    # Jupyter notebooks with pipeline and analysis
data/         # Input document corpus
results/      # Topic visualisations and coherence plots
report/       # FAI module project report
```

## Run Locally
```bash
pip install -r requirements.txt
jupyter notebook notebooks/
```

---
MSc Artificial Intelligence — NCI Dublin, 2025
