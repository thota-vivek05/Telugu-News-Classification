# Telugu News Classification using NLP

![Python](https://img.shields.io/badge/Python-3.x-blue)
![NLP](https://img.shields.io/badge/NLP-Telugu-green)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-red)

---

## 📌 Overview

This project focuses on automatic classification of Telugu news articles into five categories using Natural Language Processing (NLP) and Machine Learning techniques.

The project emphasizes:

- Manual Telugu text preprocessing
- Custom N-gram generation (1-gram to 5-gram)
- Manual frequency analysis
- Merge Sort based ranking of N-grams
- Feature extraction using Bag-of-Words
- News classification using Multinomial Naive Bayes

The dataset contains Telugu news articles categorized into:

- Business
- Sports
- Nation
- Entertainment
- Editorial

---

## 🚀 Key Features

✅ Telugu language preprocessing  
✅ Manual N-gram implementation (up to 5-grams)  
✅ Custom punctuation cleaning  
✅ Heap’s Law vocabulary analysis  
✅ Merge Sort implementation for ranking N-grams  
✅ Bag-of-Words feature extraction  
✅ Multinomial Naive Bayes classification  
✅ Visualization of vocabulary growth and N-gram statistics  

---

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Notebook Environment | Jupyter Notebook / Google Colab |
| Libraries | Pandas, NumPy, Scikit-learn, Matplotlib |
| NLP Techniques | Tokenization, N-grams, Bag-of-Words |
| ML Algorithm | Multinomial Naive Bayes |

---

# 🧠 NLP Pipeline

## 1️⃣ Data Cleaning & Preprocessing

- Removed unnecessary metadata columns
- Cleaned Telugu Unicode artifacts
- Removed newline and tab characters
- Implemented custom punctuation removal
- Encoded categorical topics into numerical labels

### Example Cleaning Operations

```python
text = text.replace('\\n', ' ')
text = text.replace('\\t', ' ')
```

---

## 2️⃣ Tokenization & Vocabulary Analysis

The Telugu corpus was tokenized manually for vocabulary analysis.

### Heap’s Law Statistics

| Metric | Count |
|---|---|
| Total Tokens | 3,137,514 |
| Unique Tokens | 346,448 |

Vocabulary growth was analyzed and visualized using Heap’s Law.

---

## 3️⃣ Manual N-Gram Generation

A major contribution of this project is the manual implementation of N-gram generation from 1-grams to 5-grams.

Instead of using direct library implementations, the project manually:

1. Tokenized each sentence
2. Generated N-grams using loops
3. Updated frequency dictionaries
4. Sorted frequencies using Merge Sort

---

# 📊 N-Gram Statistics

| N-Gram | Unique Count | Top Example | Frequency |
|---|---|---|---|
| 1-Gram | 346,448 | ('ఈ',) | 41,066 |
| 2-Gram | 1,689,529 | ('ఈ', 'సినిమా') | 2,110 |
| 3-Gram | 2,082,710 | ('పెద్ద', 'నోట్ల', 'రద్దు') | 438 |
| 4-Gram | 1,930,947 | ('ఆర్థిక', 'మంత్రి', 'అరుణ్', 'జైట్లీ') | 123 |
| 5-Gram | 1,689,453 | ('అంతకన్నా', 'దిగువన', 'మాత్రమే', 'షార్ట్', 'పొజిషన్లు') | 79 |

---

# 📈 Machine Learning Model

## Model Used

- Multinomial Naive Bayes

## Feature Extraction

- Count Vectorization
- Bag-of-Words representation

---

# 📷 Sample Outputs

## Heap's Law Graph

![Heap's Law](images/heaps_law.png)

## N-Gram Analysis

![N-Gram](images/ngram_analysis.png)

## Model Accuracy

![Accuracy](images/accuracy.png)

---

# 📂 Project Structure

```text
Telugu-News-Classification/
│
├── data/
├── notebooks/
├── images/
├── models/
├── README.md
├── requirements.txt
└── .gitignore
```

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/your-username/telugu-news-classification.git
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ How to Run

1. Upload datasets to `/content/`
2. Open notebook in Google Colab or Jupyter
3. Run all cells sequentially

---

# 🔮 Future Improvements

- Transformer-based Telugu NLP
- Deep Learning classification models
- Streamlit web deployment
- Larger Telugu corpus support
- Advanced embeddings

---

# 👨‍💻 Author

Your Name

---

# 📜 License

This project is licensed under the MIT License.
