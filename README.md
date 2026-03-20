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
Two classification models were trained and compared using 80/20 train-test split with stratification to preserve class balance

**Logistic Regression**
- max_inter = 1000 to ensure convergence
- 5-fold cross validation used during developement (Average CV accuracy: 71%)

**Naive Bayes**
- MultinomialNB since it is well suited for text classification with TF-IDF features

Both models were trained on the same vectorized features to allow for a direct comparison.

## Model Evaluation
Both models were evaluated on the same 20-review test set using accuracy, precision, recall, and F1 - score.

<img width="931" height="211" alt="image" src="https://github.com/user-attachments/assets/3d8a9010-379f-4117-9ffe-fa6b24647b6e" />

As shown on the table, although Naive Bayes had a better precision score, Logistic Regression was the overall stronger performer. It identified 91% of the psotive reviews correctly and maintained a more balanced performance.

Naive Bayes struggled significantly with negative reviews achieving only 11% recall recall for the negative class. It defaulted to predict positive majority of the time most likely because the negative review contain postive language as well. 

For this particular dataset, Logistic Regression is recommended for this dataset. 

## Sentiment Insights

## Error Analysis
## Limitations
## Reproducibility
