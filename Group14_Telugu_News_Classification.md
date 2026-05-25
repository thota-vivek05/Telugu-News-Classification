# Telugu News Classification

## 📝 Project Brief

This project classifies Telugu news articles into five categories {business, sports, nation, entertainment, editorial} using Multinomial Naive Bayes model. The core technical focus is the **manual implementation of N-gram analysis** (up to 5-grams) and customized pre-processing for the Telugu language.
The dataset used consists of Telugu news articles categorized into five topics: **business**, **sports**, **nation**, **entertainment**, and **editorial**.

---

## 🛠️ NLP Pipeline: Core Implementation

The data preprocessing and feature engineering steps for the Telugu corpus were primarily implemented using manual Python code, focusing on manual manipulation where possible to fulfill the project's complexity requirement.

### 1. Data Cleaning and Preparation

- **Initial Cleanup:** The initial columns like `SNo`, `date`, and `heading` (which contained null values) were removed.
- **Text Normalization (Manual):** Various unwanted Unicode and newline characters (`\u200c`, `\n`, `\t`, `\xa0`) were manually stripped from the `body` content to create a `body_processed` column.
- **Punctuation Removal (Manual Function):** A custom function `remove_punctuation(text)` was implemented to strip all standard punctuation marks, as they generally do not carry semantic weight in Bag-of-Words models.
- **Topic Encoding:** The categorical `topic` labels were converted to numerical IDs (`0` to `4`) using manual dictionaries (`topic_dic`, `inv_topic_dict`) for model compatibility.

### 2. Sentence and Token-Level Analysis

- **Sentence Tokenization:** A custom sentence Tokenize module was utilized to split the processed Telugu articles into individual sentences by considering common Abbrevations.
- **Vocabulary Growth Analysis (Heap's Law):** The total corpus text was tokenized, and the vocabulary growth was manually tracked against the total number of tokens to demonstrate Heap's Law. A graph of this relationship was generated.
  - **Total Tokens:** 3,137,514
  - **Unique Tokens (Vocabulary Size):** 346,448

### 3. **Manual N-Gram Generation and Analysis (Main Focus)**

The most significant NLP contribution is the manual implementation and analysis of n-grams up to **5-grams** (sequences of 1 to 5 tokens).

- **Manual Generation:** Instead of relying on built-in libraries' `ngrams` functions that directly return a list of n-gram tuples, the logic involved:
  1.  Iterating through every cleaned sentence.
  2.  Tokenizing the sentence into unigrams (`tokens`).
  3.  Using nested loops (`j` from 0 to `len(tokens) - n`) to manually construct tuples of length N (e.g., `(tokens[j], tokens[j + 1], ..., tokens[j + N-1])`).
  4.  Manually building and updating a frequency dictionary (`n_grams_telugu_vocab`) for each unique n-gram encountered.
- **Manual Sorting (Merge Sort):** The generated n-gram dictionaries were explicitly sorted in descending order of frequency using a **Merge Sort** implementation (functions `merge_sort` and `merge`) to find the most frequently occurring n-grams.

#### **N-Gram Counts and Top Results**

| N-Gram (N) | Total Unique N-Grams (Manual Count) |                     Top N-Gram Example                     | Frequency |
| :--------: | :---------------------------------: | :--------------------------------------------------------: | :-------: |
| **1-gram** |               346,448               |                      `('ఈ',)` (This)                       |  41,066   |
| **2-gram** |              1,689,529              |                     `('ఈ', 'సినిమా')`                      |   2,110   |
| **3-gram** |              2,082,710              |               `('పెద్ద', 'నోట్ల', 'రద్దు')`                |    438    |
| **4-gram** |              1,930,947              |         `('ఆర్థిక', 'మంత్రి', 'అరుణ్', 'జైట్లీ')`          |    123    |
| **5-gram** |              1,689,453              | `('అంతకన్నా', 'దిగువన', 'మాత్రమే', 'షార్ట్', 'పొజిషన్లు')` |    79     |

This rigorous, manual approach confirms the complexity of Telugu text and the diminishing returns in finding common themes at higher n-gram levels.

---

## 💻 Instructions on How to Run

### Prerequisites

- **Python Environment:** Use a Python environment, preferably **Google Colab**, where the notebook was designed.
- **Required Libraries:** Ensure these packages are installed: `pandas`, `numpy`, `re`, `sklearn`.

## Steps to Execute

1. **Environment Setup:**  
   Install all prerequisite libraries.

2. **Upload Data:**  
   Upload the main dataset (`added_telugu_articles.csv`) and the test dataset (`test_telugu_news.csv`) to the path `/content/`.

3. **Sequential Execution:**  
   Run all notebook cells in order, covering these key steps:
   - **Data Loading & Cleaning:**  
     Load the data and remove metadata or missing columns (`SNo`, `date`, `heading`).
   - **Manual N-gram Processing:**  
     Execute the cells defining the manual **Merge Sort** and the loops for generating and counting **N-grams** (`bigrams` through `5-grams`).
   - **Visualization:**  
     Run the cells that plot the **Heap's Law graph** and **N-gram counts**.

---
