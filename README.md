# IMDB-movie-reviews
## 1. Introduction and Problem Statement

This project addresses the task of sentiment analysis on the IMDB movie reviews dataset. The goal is to classify movie reviews as either positive or negative based on their textual content. Sentiment analysis has various real-world applications, including understanding customer feedback, monitoring social media sentiment, and market research.

## 2. Methodology and NLP Techniques

The Natural Language Processing (NLP) pipeline implemented in this notebook includes the following steps:

*   **Data Loading and Exploration:** The IMDB dataset containing movie reviews and their corresponding sentiment labels (positive/negative) was loaded and explored to understand its structure and distribution.
*   **Data Preprocessing:** The raw text reviews were preprocessed to remove HTML tags, non-alphabetic characters, convert text to lowercase, tokenize words, and remove common English stopwords. Additionally, the impact of **Lemmatization** as an alternative preprocessing technique was explored.
*   **Feature Representation:** Different techniques were used to convert the text data into numerical feature vectors:
    *   **TF-IDF (Term Frequency-Inverse Document Frequency):** Represents the importance of words in a document relative to a collection of documents.
    *   **Word2Vec:** A word embedding technique that learns dense vector representations of words based on their context.
    *   **fastText:** Another word embedding technique that extends Word2Vec by considering subword information, which helps in handling out-of-vocabulary words.
*   **Model Training:** Several machine learning models were trained and evaluated for the sentiment analysis task:
    *   **Logistic Regression:** A linear model used for binary classification.
    *   **Support Vector Machine (SVM):** A powerful model that finds an optimal hyperplane to separate classes.
    *   **Neural Network (Simple Feedforward):** A basic neural network with dense layers.
*   **Evaluation:** The models were evaluated using standard classification metrics, including Accuracy, F1-score, Confusion Matrix, and Classification Report.
*   **Visualization:** t-SNE (t-Distributed Stochastic Neighbor Embedding) was used to visualize the high-dimensional feature representations (TF-IDF, Word2Vec, fastText embeddings) in a 2D space to observe how well the positive and negative sentiment reviews are separated.

# 3. Results and Discussion

The models were trained and evaluated using the different feature representations and preprocessing techniques. The performance metrics (Accuracy and F1-score) were compared across the models and feature types.

*(Include a summary table or list of the key performance metrics for each model and feature combination here. For example:)*

| Model               | Feature Representation | Preprocessing   | Accuracy | F1-score |
| :------------------ | :--------------------- | :-------------- | :------- | :------- |
| Logistic Regression | TF-IDF                 | Basic           | 0.8886   | 0.8910   |
| Logistic Regression | Word2Vec               | Basic           | 0.8589   | 0.8612   |
| Logistic Regression | fastText               | Basic           | 0.8464   | 0.8486   |
| SVM                 | TF-IDF                 | Basic           | 0.8802   | 0.8825   |
| SVM                 | Word2Vec               | Basic           | 0.8585   | 0.8612   |
| SVM                 | fastText               | Basic           | 0.8472   | 0.8495   |
| Neural Network      | TF-IDF                 | Basic           | 0.8731   | -        |
| Neural Network      | Word2Vec               | Basic           | 0.8614   | -        |
| Neural Network      | fastText               | Basic           | 0.8465   | -        |
| Logistic Regression | TF-IDF                 | Lemmatization   | 0.8850   | 0.8874   |
| SVM                 | TF-IDF                 | Lemmatization   | 0.8793   | 0.8815   |
| Neural Network      | TF-IDF                 | Lemmatization   | 0.8803   | -        |
*(Note: You would fill in the F1-score for the Neural Networks after calculating them.)*

Based on the current results, Logistic Regression with TF-IDF features using basic preprocessing achieved the highest accuracy and F1-score. The t-SNE visualizations provide insights into how well the different feature spaces separate the sentiment classes.
