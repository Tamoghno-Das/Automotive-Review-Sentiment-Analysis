# 🚗 AI-Based Automotive Review & Customer Sentiment Analytics

An AI/ML-based Natural Language Processing (NLP) project that analyzes automotive reviews, identifies customer sentiment, extracts important automotive aspects, and performs **aspect-level sentiment analysis**.

The system uses a **BERT-family transformer model (DistilBERT)** for sentiment classification and a keyword-based aspect extraction approach to identify aspects such as battery, engine, mileage, safety, comfort, service, infotainment, price, charging, and range.

---

## 📌 Project Overview

Automotive customers share large amounts of feedback through online reviews. Manually analyzing these reviews to understand customer satisfaction across different vehicle features can be time-consuming.

This project provides an automated solution that analyzes a customer review and determines:

* Overall sentiment
* Sentiment confidence
* Important automotive aspects
* Sentiment associated with each aspect
* Aspect-level sentiment visualization

### Example

**Input:**

> The battery range is excellent, but the charging time is too long. The seats are comfortable, but the price is very high.

**Possible Analysis:**

| Aspect   | Sentiment |
| -------- | --------- |
| Battery  | Positive  |
| Range    | Positive  |
| Charging | Negative  |
| Comfort  | Positive  |
| Price    | Negative  |

---

## 🎯 Objectives

The main objectives of this project are:

* Analyze automotive customer reviews using NLP.
* Preprocess textual review data.
* Perform sentiment classification using a transformer-based model.
* Identify important automotive-related aspects.
* Determine sentiment associated with individual aspects.
* Visualize sentiment and aspect-level results.
* Provide an interactive review analyzer.
* Export analysis results for further use.

---

## 🧠 Technologies Used

| Technology                | Purpose                               |
| ------------------------- | ------------------------------------- |
| Python                    | Core programming language             |
| Google Colab              | Development and execution environment |
| Pandas                    | Data manipulation                     |
| NumPy                     | Numerical operations                  |
| Scikit-learn              | Dataset splitting and evaluation      |
| NLTK                      | Text preprocessing                    |
| PyTorch                   | Deep learning framework               |
| Hugging Face Transformers | BERT/DistilBERT implementation        |
| Hugging Face Datasets     | Dataset preparation                   |
| Matplotlib                | Visualization                         |
| Seaborn                   | Statistical visualization             |

---

## 🤖 Machine Learning Model

The project uses a **transformer-based language model** for sentiment classification.

### Model

```text
DistilBERT
```

DistilBERT is a lighter and faster version of BERT that can be used for text classification tasks while retaining the transformer-based architecture.

### Classification

The model classifies reviews into:

```text
POSITIVE
NEGATIVE
```

The model also provides a confidence value for its prediction.

---

## 🏗️ System Architecture

```text
                AUTOMOTIVE REVIEWS
                         │
                         ▼
                TEXT PREPROCESSING
                         │
                         ▼
                     TOKENIZER
                         │
                         ▼
                    DISTILBERT
                         │
              ┌──────────┴──────────┐
              │                     │
              ▼                     ▼
       SENTIMENT             ASPECT EXTRACTION
      CLASSIFICATION                │
              │                     │
              └──────────┬──────────┘
                         ▼
                ASPECT-LEVEL
                   SENTIMENT
                         │
                         ▼
                  VISUALIZATION
                         │
                         ▼
                   FINAL OUTPUT
```

---

## 🔍 Automotive Aspects

The system can identify several automotive-related aspects:

* Vehicle
* Engine
* Battery
* Mileage
* Safety
* Comfort
* Service
* Infotainment
* Price
* Charging
* Range

These aspects are detected using predefined automotive-related keywords.

---

## 🔄 Project Workflow

### 1. Data Collection

Automotive review text is provided as input to the system.

### 2. Text Preprocessing

The reviews are cleaned by:

* Converting text to lowercase
* Removing URLs
* Removing special characters
* Removing unnecessary spaces

### 3. Tokenization

The cleaned reviews are converted into tokens using the transformer tokenizer.

### 4. Sentiment Classification

The tokenized text is passed to the DistilBERT model.

The model predicts:

```text
Positive
```

or

```text
Negative
```

### 5. Aspect Extraction

Automotive-related aspects are identified from the review.

### 6. Aspect-Level Sentiment

The sentiment of sentences containing specific aspects is analyzed.

### 7. Visualization

Results can be displayed using charts such as:

* Sentiment distribution
* Aspect-level sentiment
* Confusion matrix

### 8. Result Export

The analysis results can be exported as CSV files.

---

## 📊 Model Evaluation

The project evaluates the sentiment classifier using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

Example evaluation:

```text
              precision    recall    f1-score

Negative          ...        ...        ...
Positive          ...        ...        ...

Accuracy           ...
```

The exact values depend on the dataset and training configuration used.

---

## 📈 Visualizations

The project generates visualizations including:

### Sentiment Distribution

Shows the distribution of positive and negative automotive reviews.

### Confusion Matrix

Shows the relationship between actual and predicted sentiment.

### Aspect-Level Sentiment

Shows how customers feel about individual vehicle aspects.

Example:

```text
Battery       → Positive
Range         → Positive
Charging      → Negative
Comfort       → Positive
Price         → Negative
```

---

## 💻 Running the Project

### Option 1 — Google Colab

This project was designed to run easily in Google Colab.

1. Open the project notebook in Google Colab.
2. Install the required libraries.
3. Run the cells sequentially.
4. Train the model.
5. Test the sentiment classifier.
6. Enter an automotive review.
7. View the aspect-level sentiment results.

### Install Dependencies

```bash
pip install transformers datasets accelerate torch scikit-learn pandas numpy matplotlib seaborn nltk wordcloud
```

---

## 📁 Suggested Repository Structure

```text
Automotive-Review-Sentiment-Analytics/
│
├── Automotive_Review_Sentiment_Analytics.ipynb
│
├── data/
│   └── automotive_reviews_dataset.csv
│
├── results/
│   └── automotive_review_analysis.csv
│
├── README.md
│
└── requirements.txt
```

---

## 📝 Example Usage

After running the notebook, enter a review such as:

```text
The battery range is excellent but the charging time is too long.
The seats are comfortable but the price is very high.
```

The system processes the review and produces:

```text
Overall Sentiment: NEGATIVE

Aspect-Level Sentiment:

Battery      → POSITIVE
Range        → POSITIVE
Charging     → NEGATIVE
Comfort      → POSITIVE
Price        → NEGATIVE
```

---

## 📤 Exporting Results

The project can save aspect-level analysis to:

```text
automotive_review_analysis.csv
```

Example structure:

```text
Aspect,Sentiment,Confidence,Sentence
Battery,POSITIVE,XX.XX,The battery range is excellent.
Charging,NEGATIVE,XX.XX,The charging time is too long.
```

---

## 📚 Dataset

The notebook contains a demonstration automotive-review dataset for development and testing.

The project can also be adapted to a larger real-world automotive review dataset for improved model training and evaluation.

> **Note:** The generated/template review dataset used during development is intended for demonstration and project development. It should not be interpreted as a representative real-world customer population.

---

## ⚠️ Limitations

The current implementation has several limitations:

* The demonstration dataset is relatively small.
* Aspect extraction currently uses predefined automotive keywords.
* The sentiment classifier focuses on positive and negative sentiment.
* Complex sentences containing multiple conflicting sentiments may require more advanced aspect-based sentiment modeling.
* Real-world performance depends heavily on the quality and size of the training dataset.

---

## 🚀 Future Improvements

Possible future improvements include:

* Use a significantly larger real-world automotive review dataset.
* Fine-tune BERT on domain-specific automotive reviews.
* Add **XLM-R** for multilingual automotive reviews.
* Add neutral sentiment classification.
* Replace keyword-based aspect extraction with an NLP-based aspect extraction model.
* Implement Named Entity Recognition (NER).
* Add multilingual support.
* Build a Streamlit web application.
* Add real-time review analysis.
* Store reviews and analytics in a database.
* Create an interactive analytics dashboard.
* Add automatic review summarization.
* Deploy the model as a REST API.

---

## 🌐 Potential Applications

This system can be useful for:

* Automotive companies
* Vehicle manufacturers
* Dealerships
* Customer feedback analysis
* Product research
* Market research
* Customer experience teams
* Vehicle comparison platforms
* Automotive review websites

Companies could use such a system to identify frequently praised or criticized vehicle features from large collections of customer reviews.

---

## 📌 Project Highlights

```text
✔ NLP-based automotive review analysis
✔ Transformer-based sentiment classification
✔ DistilBERT
✔ Automotive aspect extraction
✔ Aspect-level sentiment analysis
✔ Confidence scoring
✔ Confusion matrix
✔ Sentiment visualization
✔ CSV result export
✔ Interactive review analyzer
✔ Google Colab compatible
```

---

## 🧪 Sample Test Reviews

### Positive

```text
The engine performance is excellent and the mileage is impressive.
```

### Negative

```text
The battery range is poor and charging takes too long.
```

### Mixed Review

```text
The battery range is excellent, but the charging time is too long.
The seats are comfortable, but the price is very high.
```

---

## 👨‍💻 Author

**Tamoghno Das**

B.Tech Computer Science & Engineering

---

## ⭐ Acknowledgement

This project was developed as part of a **Module 3 Connectivity Project** focused on applying AI/ML and NLP techniques to the automotive domain.

---

## 📄 License

This project is intended for educational and demonstration purposes.

You are free to modify and extend the project for learning and experimentation.

