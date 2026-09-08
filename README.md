# Financial News Sentiment Analysis Using NLP and Machine Learning

## 📌 Project Overview

This project focuses on developing a **Financial News Sentiment Analysis system** using Natural Language Processing (NLP) and Machine Learning techniques.

The system analyzes financial news sentences and classifies them into three sentiment categories:

* **Positive**
* **Negative**
* **Neutral**

The project uses the **Financial PhraseBank** dataset and applies text preprocessing, exploratory data analysis, TF-IDF feature extraction, and machine learning classification algorithms.

A **Support Vector Machine (SVM)** model was selected as the final model based on its performance and was integrated into a simple web-based interface using **Gradio**.

---

## 🎯 Objectives

The main objectives of this project are:

1. To preprocess and clean financial news text using NLP techniques.
2. To explore and analyze the distribution and characteristics of the financial news dataset.
3. To convert textual data into numerical features using **TF-IDF**.
4. To train and compare different machine learning classification models.
5. To evaluate model performance using accuracy, precision, recall, and F1-score.
6. To identify important words associated with different sentiment categories.
7. To develop a simple Gradio web application for real-time sentiment prediction.

---

## 📊 Dataset

The project uses the **Financial PhraseBank** dataset.

The dataset contains financial news sentences labelled according to their sentiment. The three sentiment categories are:

| Sentiment | Description                                                                                 |
| --------- | ------------------------------------------------------------------------------------------- |
| Positive  | Financial information indicating favourable business or financial conditions                |
| Negative  | Financial information indicating unfavourable business or financial conditions              |
| Neutral   | Factual or objective financial information without a clearly positive or negative sentiment |

The dataset file used in this project is:

```text
Sentences_75Agree.txt
```

The original dataset contains financial news sentences annotated by human annotators.

### Dataset Source

## Dataset Source

The dataset can be accessed from the following GitHub repository:  
[Financial PhraseBank Dataset Repository](https://github.com/maxwellsarpong/NLP-financial-text-processing-dataset)

The original Financial PhraseBank dataset contains financial and economic sentences annotated as positive, negative, or neutral. For this project, the `Sentences_75Agree.txt` version was used.

The dataset was originally introduced in the following study:
> Malo, P., Sinha, A., Korhonen, P., Wallenius, J., and Takala, P. (2014). *Good debt or bad debt: Detecting semantic orientations in economic texts.* Journal of the American Society for Information Science and Technology, 65(4), 782–796.

---

## 🔄 Project Workflow

The overall workflow of the project is:

```text
Financial News Dataset
        ↓
Data Loading
        ↓
Data Cleaning
        ↓
Duplicate Removal
        ↓
Text Preprocessing
        ↓
Exploratory Data Analysis
        ↓
TF-IDF Feature Extraction
        ↓
Train-Test Split
        ↓
Machine Learning Models
        ↓
Model Evaluation
        ↓
Model Comparison
        ↓
SVM Model Selection
        ↓
Gradio Web Application
        ↓
Sentiment Prediction
```

---

## 🧹 Data Preprocessing

The following preprocessing techniques were applied to the financial news text:

* Conversion of text to lowercase
* Removal of unnecessary characters
* Tokenization
* Stopword removal
* Removal of punctuation
* Lemmatization
* Duplicate removal
* Removal of empty cleaned text

After preprocessing and cleaning, the final dataset contained **3,447 records**.

The final sentiment distribution was:

* Neutral: **2,140**
* Positive: **887**
* Negative: **420**

---

## 📈 Exploratory Data Analysis

Several visualizations were created to understand the dataset, including:

* Sentiment distribution
* Word-count distribution
* Most frequently occurring words
* Overall word cloud
* Positive sentiment word cloud
* Negative sentiment word cloud
* Neutral sentiment word cloud

These visualizations helped identify common financial terms and understand the characteristics of each sentiment category.

---

## 🔢 Feature Extraction

The cleaned text was converted into numerical features using **Term Frequency-Inverse Document Frequency (TF-IDF)**.

The configuration used was:

```text
max_features = 5000
ngram_range = (1, 2)
min_df = 2
```

Both individual words (unigrams) and two-word combinations (bigrams) were considered.

The resulting feature matrices contained **5,000 TF-IDF features**.

---

## 🤖 Machine Learning Models

Three machine learning classification algorithms were trained and evaluated:

1. Multinomial Naive Bayes
2. Logistic Regression
3. Linear Support Vector Machine (SVM)

The dataset was divided into:

```text
Training data: 2,757 records
Testing data:    690 records
```

A stratified train-test split with a test size of 20% and `random_state=42` was used.

---

## 📊 Model Performance

The models were evaluated using Accuracy, Precision, Recall, and F1-score.

| Model                   |   Accuracy |  Precision |     Recall |   F1-Score |
| ----------------------- | ---------: | ---------: | ---------: | ---------: |
| Multinomial Naive Bayes |     77.83% |     78.96% |     77.83% |     75.28% |
| Logistic Regression     |     81.74% |     82.59% |     81.74% |     80.20% |
| **Linear SVM**          | **82.90%** | **82.76%** | **82.90%** | **82.23%** |

Based on the evaluation results, **Linear SVM achieved the best overall performance** and was selected as the final model.

---

## 🔍 SVM Classification Results

The final SVM model achieved:

```text
Accuracy  : 82.90%
Precision : 82.76%
Recall    : 82.90%
F1-Score  : 82.23%
```

The model performed particularly well in identifying the **Neutral** class. However, the Negative class had lower recall compared with the other classes, which indicates that some negative financial statements were incorrectly classified as Neutral or Positive.

---

## 🔤 Important Features

The model identified several words that were strongly associated with different sentiment categories.

### Negative Sentiment

Examples include:

```text
decline
loss
decreased
dropped
fell
lower
weak
declined
operating loss
```

### Neutral Sentiment

Examples include:

```text
company
value
pension
facility
approximately
include
business
service
```

### Positive Sentiment

Examples include:

```text
increase
rose
improved
growth
positive
grew
signed
awarded
better
```

These features provide insight into the types of financial terms associated with different sentiment categories.

---

## 🌐 Gradio Web Application

A simple web application was developed using **Gradio** to make the trained sentiment classification model easier to use.

The application is called:

```text
Financial News Sentiment Analyzer
```

Users can enter a financial news sentence, and the application processes the text using the same preprocessing and TF-IDF transformation pipeline used during model development.

The trained SVM model then predicts one of the following:

```text
Positive
Negative
Neutral
```

### Example

Input:

```text
The company's revenue increased significantly and profits reached a record high.
```

Expected prediction:

```text
Positive
```

Another example:

```text
The company reported a significant decline in revenue and operating profit.
```

Expected prediction:

```text
Negative
```

The Gradio application was developed and launched from **Google Colab** using a temporary public URL.

---

## 🖥️ Application Screenshots

### Main Interface

![Gradio Interface](screenshots/gradio_interface.png)

### Positive Prediction

![Positive Prediction](screenshots/positive_prediction.png)

### Negative Prediction

![Negative Prediction](screenshots/negative_prediction.png)

---

## 🛠️ Technologies Used

### Programming Language

* Python

### Data Processing

* Pandas
* NumPy

### Natural Language Processing

* NLTK

### Machine Learning

* Scikit-learn
* Multinomial Naive Bayes
* Logistic Regression
* Linear SVM
* TF-IDF

### Data Visualization

* Matplotlib
* Seaborn
* WordCloud

### Web Application

* Gradio

### Development Environment

* Google Colab
* Jupyter Notebook

---

## 🚀 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/financial-news-sentiment-analysis.git
```

### 2. Navigate to the Project Folder

```bash
cd financial-news-sentiment-analysis
```

### 3. Install the Required Libraries

```bash
pip install -r requirements.txt
```

### 4. Open the Notebook

Open:

```text
NLP_Mini_Project.ipynb
```

using Jupyter Notebook, JupyterLab, or Google Colab.

### 5. Run the Notebook

Run the cells sequentially to:

* Load the dataset
* Preprocess the text
* Perform EDA
* Extract TF-IDF features
* Train the machine learning models
* Evaluate the models
* Run the Gradio application

---

## 📌 Limitations

* The dataset contains a relatively limited number of financial news sentences.
* The sentiment classes are imbalanced, with Neutral being the largest class.
* The model may have difficulty identifying subtle or ambiguous financial sentiment.
* The Gradio application uses a temporary public URL when launched through Google Colab.
* The model is trained specifically on financial text and may not perform well on general-domain text.

---

## 🔮 Future Improvements

Possible future improvements include:

* Applying advanced transformer-based NLP models such as BERT.
* Using class-balancing techniques to improve minority-class performance.
* Hyperparameter tuning of the machine learning models.
* Using a larger and more diverse financial news dataset.
* Deploying the application using a permanent hosting service.
* Adding confidence/probability scores using a properly calibrated model.
* Developing a more advanced user interface.

---

## 👩‍💻 Author

**Chamudi Bhawanthi**

BSc (Hons) in Data Science
Sabaragamuwa University of Sri Lanka

---


