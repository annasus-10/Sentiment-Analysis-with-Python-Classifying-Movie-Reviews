# Sentiment Analysis with Python: Classifying Movie Reviews

## Overview
This project demonstrates sentiment analysis on IMDB movie reviews using Python and deep learning. The objective is to classify reviews as positive or negative by leveraging NLP techniques and advanced neural network architectures.

## Dataset
- **Dataset Used:** [IMDB Dataset of 50K Movie Reviews on Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)
- **Columns:**  
  - `review`: Text of the movie review  
  - `sentiment`: Label (`positive`/`negative`)
- **Data Split:** 80% training, 20% testing  
- **Distribution:** Balanced between positive and negative sentiment reviews

## Data Preprocessing
- **Text Normalization:** Lowercased, removed URLs, special characters, and extra spaces  
- **Stop Words Removal:** Customized list; negation words like "not" and "no" preserved  
- **Punctuation Removal:** All punctuation removed for consistency  
- **Lemmatization:** Used to preserve base word meanings  
- **Tokenization & Padding:**  
  - Vocabulary size: 30,000 words  
  - Maximum sequence length: 100  
  - Post-padding for alignment in GRU layers

## Model Architecture
- **Embedding Layer:** 64-dimensional word vectors  
- **Convolutional Neural Network (CNN) Layer:**  
  - 256 filters  
  - Kernel size: 3  
- **Bidirectional GRU Layers:**  
  - GRU 1: 128 units (returns sequences)  
  - GRU 2: 64 units (returns sequences)  
  - GRU 3: 64 units (final output)  
  - Bidirectional configuration for improved context  
- **Dropout:** 0.3 after each GRU to reduce overfitting  
- **Dense Layers:**  
  - Dense 1: 64 units, ReLU  
  - Dense 2: 128 units, ReLU  
  - Output: 1 unit, Sigmoid (binary classification)
- **Loss Function:** Binary cross-entropy  
- **Optimizer:** Adam  
- **Early Stopping:** Monitors validation loss, with patience of 3 epochs

## Training Details
- **Epochs:** 15  
- **Batch Size:** 250  
- **Validation Split:** 10%  
- **Early Stopping:** Applied to prevent overfitting

## Results
- **F1-Score:** 0.81

## Reference
- [Sentiment Analysis on IMDB Movie Reviews: A Beginner’s Guide](https://medium.com/@AMustafa4983/sentiment-analysis-on-imdb-movie-reviews-a-beginners-guide-d5136ec74e5)
