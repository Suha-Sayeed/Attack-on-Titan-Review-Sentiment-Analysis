# Attack-on-Titan-Review-Sentiment-Analysis

## Project Overview
Sentiment classification of anime reviews using TF-IDF feature extraction with Logistic Regression and Naive Bayes.  This project investigates how well common sentiment classification models can identify positive and negative sentiment in 100 Attack on Titans Season 1 reviews collected from MyAnimeList (MAL). 

## Dataset
This project uses 100 Attack on Titan Season 1 reviews collected from MyAnimeList (MAL).

Dataset composition:
- 53 positive reviews
- 47 negative reviews

Reviews were manually collected from the MAL review page on **February 28, 2026**.

Labeling criteria:
- Reviews with scores **8–10** were labeled as **positive**
- Reviews with scores **1–4** were labeled as **negative**
- Reviews with scores **5–7 were excluded** to avoid neutral sentiment

Because MAL contains significantly more positive than negative reviews, manual sampling was performed to obtain a roughly balanced dataset.

## Data Preprocessing
### Preprocessing Steps used:
- Lowercasing: to make it all lower case
- Regex Cleaning:
    - remove special characters
    - remove numbers
    - remove symbols
    - whitespace normalization
    - standardizing formats.
- Tokenization and vocaublary creation: turning clean text into numerical feature vectors

### Preprocessing steps not done:
- Stemming or lemmatization was not applied because TF-IDF with raw tokens provided sufficent feature representation for this small dataset. 

## Feature Engineering
Text data was converted into numerical features using TF-IDF (Term Frequency - Inverse Document Frequency) vectorization

TF-IDF works by assigning higher weights to words that appear frequently in a specific review but rarely across all reviews. This makes distinctive words more meaningful compared to common words.

Configuration used:
- English stopwords removed during vectorization
- No maximum feature limit set
- Unigrams only

This produced a sparse matrix where each review is represented as weighted vector.

## Models
Two 

## Model Evaluation
## Sentiment Insights
## Error Analysis
## Limitations
## Reproducibility
