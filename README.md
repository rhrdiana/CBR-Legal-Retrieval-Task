# CBR-Putusan: Case-Based Reasoning for Indonesian Criminal Court Decisions

> **Case-Based Reasoning (CBR) System** for retrieving similar criminal court decisions and predicting judicial outcomes using **TF-IDF**, **SVM**, and **IndoBERT** representations.

---

## Overview

This project implements a **Case-Based Reasoning (CBR)** system to support legal decision retrieval on Indonesian Supreme Court (Mahkamah Agung RI) criminal cases.

The system follows the standard CBR cycle:

1. **Case Base Construction**
2. **Case Representation**
3. **Case Retrieval**
4. **Case Solution Reuse**
5. **Evaluation**

The dataset consists of criminal cassation decisions (Kasasi Pidana) obtained from the **Direktori Putusan Mahkamah Agung Republik Indonesia**.

---

## Features

* PDF extraction and preprocessing
* Automatic case base construction
* Legal case representation
* TF-IDF based retrieval
* SVM-based retrieval
* IndoBERT semantic retrieval
* Majority Voting prediction
* Weighted Similarity prediction
* Retrieval evaluation (Hit@K / Recall)
* Prediction result generation

---

## Project Structure

```
CBR_Project/
│
├── data/
│   ├── pdf/                  # Original PDF court decisions
│   ├── raws/                 # Extracted text files
│   ├── processed/            # Processed datasets & embeddings
│   │   ├── cases.csv
│   │   ├── cases_clean.csv
│   │   ├── bow_features.csv
│   │   └── bert_embeddings.npy
│   │
│   ├── eval/
│   │   ├── queries.json
│   │   ├── retrieval_results.json
│   │   └── retrieval_metrics.csv
│   │   ├── prediction_metrics.csv
│   │   └── retrieval_results_detail.json
│   │
│   └── results/
│       └── predictions.csv
│
├── notebooks/
│   ├── 01_case_base.ipynb
│   ├── 02_case_representation.ipynb
│   ├── 03_case_retrieval.ipynb
│   ├── 04_case_solution_reuse.ipynb
│   └── 05_model_evaluation.ipynb
│
├── logs/
│   └── cleaning.log
│
├── requirements.txt
└── README.md
```

---

## Workflow

### Stage 1 — Case Base Construction

Build the legal case base from PDF court decisions.

**Output**

* Extracted text files
* Cleaned legal documents
* Case metadata

---

### Stage 2 — Case Representation

Generate document representations using:

* Bag-of-Words
* TF-IDF
* SVM Features
* IndoBERT Embeddings

**Output**

* `cases.csv`
* `cases_clean.csv`
* `bow_features.csv`
* `tfidf_matrix.npz`
* `bert_embeddings.npy`

---

### Stage 3 — Retrieval

Retrieve Top-K most similar legal cases using:

* TF-IDF + Cosine Similarity
* SVM Representation
* IndoBERT Embedding + Cosine Similarity

Evaluation uses predefined queries stored in:

```
data/eval/queries.json
```

---

### Stage 4 — Case Solution Reuse

Predict judicial outcomes based on retrieved cases using:

* Majority Voting
* Weighted Similarity Voting

Prediction results are saved to:

```
data/results/predictions.csv
```

---

### Stage 5 — Evaluation

Evaluate system performance using:

* Hit@K
* Recall@K
* Retrieval comparison
* Prediction comparison

Generated evaluation files include:

* `retrieval_metrics.csv`
* `retrieval_results.json`
* `predictions.csv`

---

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd CBR_Project
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Requirements

Main libraries used:

* Python 3.10+
* PyMuPDF
* Pandas
* NumPy
* Scikit-learn
* PyTorch
* HuggingFace Transformers
* Jupyter Notebook

---

## Running the Project

Execute the notebooks sequentially:

```
01_case_base.ipynb
        ↓
02_case_representation.ipynb
        ↓
03_case_retrieval.ipynb
        ↓
04_case_solution_reuse.ipynb
        ↓
05_model_evaluation.ipynb
```

---

## Dataset

Source:

**Direktori Putusan Mahkamah Agung Republik Indonesia**

Domain:

* Criminal Law
* Cassation Decisions (Kasasi Pidana)

---

## Developers

**Herdiana Dwi Maharani**

**Nur Indah Amelia Agustin**

---

## Academic Information

**Course**

Penalaran Komputer

**Topic**

Case-Based Reasoning (CBR)

**Case Domain**

Indonesian Criminal Court Decisions (Kasasi Pidana)

