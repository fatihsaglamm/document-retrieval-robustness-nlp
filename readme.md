# 📰 Document Retrieval Robustness with TF-IDF and Word2Vec

An NLP information retrieval project that compares TF-IDF and Word2Vec document representations under different noise conditions.

The project uses the BBC News Dataset and evaluates how robust different document representations are when text is partially corrupted through token deletion or stopword removal.

## 📌 About the Project

This project investigates the robustness of document representations for information retrieval.

The main workflow includes:

- Loading and preprocessing the BBC News Dataset
- Building TF-IDF document representations
- Training Word2Vec embeddings
- Creating document embeddings from word vectors
- Injecting controlled noise into text
- Applying PCA for dimensionality reduction
- Retrieving documents using cosine similarity
- Evaluating retrieval performance

## 📚 Dataset

The project uses the **BBC News Dataset**, containing approximately 2,200 news articles.

The main categories are:

- Business
- Entertainment
- Politics
- Sport
- Tech

The notebook loads **2,226 documents** in total.

## 🧹 Text Preprocessing

Documents are preprocessed using NLTK.

The preprocessing pipeline includes:

- Tokenization
- Lowercasing
- Keeping alphabetic tokens
- Optional stopword removal

Example:

```text
Original:
The quick brown fox jumps over the lazy dog!

Processed:
the quick brown fox jumps over the lazy dog
```

## 🔢 TF-IDF Representation

TF-IDF vectors are created using Scikit-learn.

The implementation uses parameters such as:

```text
min_df = 3
max_df = 0.9
ngram_range = (1, 2)
```

The resulting TF-IDF representation contains tens of thousands of features.

## 🧠 Word2Vec Representation

A Word2Vec model is trained on the processed BBC News documents.

The model uses:

```text
Vector size: 100
Window size: 5
Minimum count: 2
Skip-gram: enabled
```

Document embeddings are created by averaging the Word2Vec vectors of the words contained in each document.

## 🌪️ Noise Injection

The project tests representation robustness by introducing different forms of noise.

### Token Deletion

Three token deletion levels are used:

```text
10% token deletion
20% token deletion
30% token deletion
```

### Stopword Removal

Stopwords are removed using the NLTK English stopword list.

The noisy document versions are then compared with the original clean representation.

## 📉 PCA Dimensionality Reduction

Principal Component Analysis (PCA) is applied to both:

- TF-IDF representations
- Word2Vec document embeddings

Two variance thresholds are tested:

```text
80% retained variance
90% retained variance
```

This allows the project to examine whether dimensionality reduction improves or reduces robustness under noisy conditions.

## 🔍 Information Retrieval

The project implements a document retrieval system using **cosine similarity**.

Queries are created for all five BBC News categories.

Example queries include:

```text
stock market economy
film music dance
football basketball referee
computer AI application
election government parliament
```

For each query, the system ranks documents according to similarity.

## 📊 Evaluation

The retrieval system is evaluated using information retrieval metrics including:

- Precision@k
- Recall@k
- Average Precision
- Mean Average Precision (MAP)

Different representations are compared under multiple conditions:

```text
TF-IDF
TF-IDF + PCA 80%
TF-IDF + PCA 90%

Word2Vec
Word2Vec + PCA 80%
Word2Vec + PCA 90%
```

Each representation is tested under:

```text
Clean text
10% token deletion
20% token deletion
30% token deletion
Stopword removal
```

## 📈 Observations

The experiments compare how TF-IDF and Word2Vec react to noisy input.

The notebook's analysis indicates that:

- Word embeddings are generally more robust to token deletion.
- Stopword removal causes relatively small changes compared with random token deletion.
- PCA can affect TF-IDF and Word2Vec representations differently.
- Token deletion tends to be more damaging than stopword removal.

## 🛠 Technologies & Libraries

- Python
- Jupyter Notebook / Google Colab
- NLTK
- NumPy
- Pandas
- Scikit-learn
- Gensim
- Word2Vec
- Matplotlib

## 🧩 Key Concepts

This project demonstrates:

- Natural Language Processing
- Information Retrieval
- TF-IDF
- Word Embeddings
- Word2Vec
- Document Embeddings
- Cosine Similarity
- Noise Robustness
- Token Deletion
- Stopword Removal
- PCA
- Dimensionality Reduction
- Precision@k
- Recall@k
- Mean Average Precision

## 📂 Project Structure

```text
document-retrieval-robustness-nlp/
│
├── document-retrieval-robustness.ipynb
└── README.md
```

## ▶️ Running the Project

Open:

```text
document-retrieval-robustness.ipynb
```

using one of the following:

- Google Colab
- Jupyter Notebook
- JupyterLab
- VS Code

Then run the notebook cells in order.

The notebook downloads the required BBC News Dataset and NLTK resources automatically.

## 🎓 Course Project

Developed as part of:

**CNG463 - Introduction to Natural Language Processing**

Middle East Technical University, Northern Cyprus Campus.

## 👤 Author

Fatih Sağlam