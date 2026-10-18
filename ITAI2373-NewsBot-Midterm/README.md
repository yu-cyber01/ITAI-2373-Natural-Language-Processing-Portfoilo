# NewsBot Intelligence System

## Project Overview

NewsBot Intelligence System is a Python-based Natural Language Processing (NLP) project that analyzes news articles. It combines several NLP techniques to classify articles by topic, identify named entities, analyze sentiment, and produce useful information about article content.

I developed this project to learn how different NLP techniques work individually and how they can be combined into one system. The project also helped me understand the challenges of building and evaluating machine learning models.

## Project Objectives

- Prepare and analyze news article text using NLP preprocessing techniques.
- Classify articles into five news categories.
- Identify people, organizations, locations, and other named entities in articles.
- Analyze the sentiment of news text.
- Combine multiple NLP tasks into one news analysis workflow.
- Evaluate model performance and recognize limitations in real-world testing.

## Dataset

The project uses **1,440 BBC news articles** from five categories:

- Business
- Entertainment
- Politics
- Sport
- Tech

The articles were used to explore text preprocessing, feature extraction, classification, and other NLP tasks.

## Technologies and Libraries

- **Python** — main programming language
- **Google Colab / Jupyter Notebook** — development environment
- **scikit-learn** — TF-IDF features, classification models, and evaluation
- **spaCy** — named entity recognition and linguistic analysis
- **NLTK VADER** — sentiment analysis

## NLP Techniques Used

### 1. Text Preprocessing

Prepared article text for analysis and machine learning.

### 2. TF-IDF Feature Extraction

Converted article text into numerical features that classification models can use.

### 3. Part-of-Speech Tagging and Syntactic Analysis

Explored grammatical information and sentence structure.

### 4. Text Classification

Compared three machine learning algorithms:

- Logistic Regression
- Support Vector Machine (SVM)
- Naive Bayes

The classifier predicts whether an article belongs to Business, Entertainment, Politics, Sport, or Tech.

### 5. Sentiment Analysis

Used VADER to estimate the sentiment of news text.

### 6. Named Entity Recognition (NER)

Used spaCy to identify entities such as people, companies, and locations mentioned in articles.

### 7. System Integration

Combined preprocessing, category prediction, sentiment analysis, named entity recognition, and generated insights into the NewsBot workflow.

## Model Performance

A tuned **Logistic Regression** classifier with **C = 100** and **5,000 TF-IDF features** achieved **97.22% accuracy** on the held-out test set (**280 out of 288 articles classified correctly**).

**Important:** The final integrated NewsBot used the original Logistic Regression configuration (**C = 1**, with **5,007 input features**), not the tuned model. Therefore, the 97.22% result should not be interpreted as the measured accuracy of the final integrated version.

## Final System Testing

I tested the integrated system using short sample news articles:

| Sample article | Predicted category | Confidence | Observation |
| --- | --- | ---: | --- |
| Microsoft acquires an AI startup | Business | 42.96% | Business is plausible, but Tech could also fit. |
| Lakers win a championship | Business | 32.89% | Incorrect; Sport would be expected. |
| Climate change report | Business | 42.29% | The topic could fit more than one category depending on the article's focus. |

All three short examples were classified as Business with confidence below 50%. These tests showed that the system can run its NLP workflow while still producing uncertain or incorrect predictions.

One possible explanation is that the short samples contained only a title and a few sentences, while the training articles were much longer (about 402 words on average). Differences between the original and tuned classifier configurations may also matter. These are possible factors, not confirmed causes.

## Challenges and Lessons Learned

- **Understanding TF-IDF:** Learning how text is represented as numerical features took time.
- **Entity-sentiment associations:** It was challenging to understand how sentiment could be associated with individual entities and how that information should be interpreted.
- **Combining NLP tasks:** Integrating several techniques helped me see how they work together in a complete application.
- **Model limitations:** High test accuracy did not guarantee correct predictions on every new article, especially short examples.
- **Human oversight:** AI-generated results should be reviewed rather than treated as automatically correct.

## Potential Applications

- Help news organizations organize articles into categories.
- Make it easier for readers to find articles about topics they care about.
- Help students and researchers identify people or organizations mentioned in articles who may be relevant to further research.
- Support news analysis by combining topic classification, sentiment, and entity extraction.

## Future Improvements

- Test and compare the tuned classifier inside the complete NewsBot system.
- Evaluate the system with more examples, including short articles and articles that fit multiple categories.
- Improve handling of uncertain predictions and low confidence scores.
- Review named entity recognition and sentiment outputs for errors.
- Explore ways to make the system easier to use.

## Project Status

**Course project completed.** Further improvements and testing are possible.
