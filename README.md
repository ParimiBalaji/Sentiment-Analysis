# Sentiment Analysis using LSTM Model

![Sentiment Analysis](https://img.shields.io/badge/Sentiment-Analysis-brightgreen.svg)
![Python](https://img.shields.io/badge/Made%20with-Python-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![No Credentials](https://img.shields.io/badge/No%20AWS%2FKaggle-Credentials%20Needed-success.svg)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ParimiBalaji/Sentiment-Analysis/blob/main/Sentiment_Analysis_LSTM_Keras_Builtin.ipynb)

> **Zero credential setup** — uses the IMDB dataset built directly into Keras. Just run and go!

---

## Table of Contents

- [Introduction](#introduction)
- [Learning Objectives](#learning-objectives)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Usage](#usage)
- [Requirements](#requirements)
- [License](#license)

---

## Introduction

Sentiment analysis is a Natural Language Processing (NLP) task that determines whether a piece of text expresses a **positive** or **negative** opinion.

This project uses an **LSTM (Long Short-Term Memory)** neural network — a type of Recurrent Neural Network (RNN) — to classify movie reviews from the IMDB dataset as positive or negative.

Unlike many similar projects, **this version requires no AWS, Kaggle, or any other external credentials**. The IMDB dataset is loaded directly from `tensorflow.keras.datasets.imdb`.

---

## Learning Objectives

By the end of this project, you will be able to:

- Load and explore a built-in NLP dataset from Keras
- Understand how text is encoded as integer sequences
- Apply sequence padding to prepare data for an LSTM
- Build, train, and evaluate an LSTM classification model
- Predict sentiment on custom text inputs

---

## Dataset

| Property        | Value |
|-----------------|-------|
| Source          | `tensorflow.keras.datasets.imdb` |
| Total Samples   | 50,000 movie reviews |
| Train / Test    | 25,000 / 25,000 |
| Vocabulary Size | Top 10,000 most frequent words |
| Label           | `1` = Positive, `0` = Negative |
| Class Balance   | Perfectly balanced (50% each) |

---

## Project Workflow

```
1. Import Libraries
        ↓
2. Load IMDB Dataset (Keras built-in, no credentials)
        ↓
3. Exploratory Data Analysis
   - Class distribution
   - Review length distribution
   - Decode sample reviews to text
        ↓
4. Sequence Padding (maxlen = 200)
        ↓
5. Build LSTM Model
        ↓
6. Train (5 epochs, batch_size=128, 20% validation)
        ↓
7. Plot Accuracy & Loss curves
        ↓
8. Evaluate on Test Set
        ↓
9. Predict on Custom Reviews
```

---

## Model Architecture

```
Input  (sequence of 200 integer tokens)
  ↓
Embedding Layer    (10,000 vocab → 32 dimensions)
  ↓
LSTM Layer         (64 units, dropout=0.2, recurrent_dropout=0.2)
  ↓
Dense Layer        (1 unit, sigmoid activation)
  ↓
Output             (probability: 0=negative, 1=positive)
```

**Loss function:** Binary Cross-Entropy  
**Optimizer:** Adam  
**Metric:** Accuracy

---

## Results

| Metric         | Value   |
|----------------|---------|
| Test Accuracy  | ~86%+   |
| Test Loss      | ~0.31   |
| Epochs Trained | 5       |

---

## Usage

### Option 1 — Google Colab (Recommended, Zero Setup)

Click the **Open in Colab** badge at the top. All dependencies are pre-installed in Colab.

### Option 2 — Run Locally

1. **Clone this repository:**
   ```bash
   git clone https://github.com/ParimiBalaji/Sentiment-Analysis.git
   cd Sentiment-Analysis
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Open the notebook:**
   ```bash
   jupyter notebook Sentiment_Analysis_LSTM_Keras_Builtin.ipynb
   ```

4. **Run all cells** — the dataset downloads automatically on first run (~17 MB).

---

## Requirements

```
tensorflow>=2.10
numpy
matplotlib
seaborn
jupyter
```

Install all at once:
```bash
pip install -r requirements.txt
```

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contributing

Contributions are welcome! Feel free to open an issue or pull request.

---

Happy coding! 🎬🤖
