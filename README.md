# Analytics Firm Clients Projects

## Project Overview

This repository contains a collection of data science projects developed around three realistic business challenges within a mid-sized analytics firm

The projects explore how different data types and ML techniques can be used to extract meaningful insights, understand customer behavior, analyze historical trends, and support data-driven decision-making

The project covers three key areas of data science:

1. **Natural Language Processing (NLP):** Extracting insights from unstructured customer reviews through text preprocessing, word frequency analysis, and bigram extraction
2. **Time Series Analysis:** Examining customer review activity and rating patterns over time to identify trends and changes in customer feedback
3. **Neural Network Modeling:** Applying deep learning techniques to classify customer reviews based on their numerical ratings

## Business Scenario

A mid-sized analytics firm receives requests from clients who need help solving different data-related problems

This project simulates three engagements in which a junior data scientist is expected to collect, preprocess, analyze, and model real-world data to produce actionable business insights

For this implementation, a customer reviews dataset is used to explore text analytics, temporal patterns, and neural network classification

## Project Objectives

- Apply NLP techniques to extract meaningful information from customer reviews
- Identify frequently discussed topics and product-related concerns
- Analyze changes in customer review volumes and ratings over time
- Understand how temporal patterns can support business monitoring
- Build a neural network model to predict customer ratings from review text
- Evaluate model performance and identify limitations affecting its reliability
- Translate analytical findings into practical business recommendations

## Project Structure

```text
analytics_firm_client_projects/
│
├── data/
│   └── amazon_reviews_lab.csv
│
├── analytics_firm_clients.ipynb
│   
│
├── README.md
├── requirements.txt
└── .gitignore
```

## Dataset

**Dataset:** Amazon Customer Reviews

The dataset contains 997 customer review records and 9 columns, including:

| Column | Description |
|---|---|
| `product_id` | Identifier of the reviewed product |
| `rating` | Numerical customer rating (1–5) |
| `review_text` | Full customer review |
| `review_summary` | Short review summary |
| `review_time_raw` | Original review date representation |
| `unix_review_time` | Unix timestamp |
| `timestamp` | Converted review date |
| `sentiment_label` | Sentiment category |
| `review_length_words` | Number of words in the review |

The dataset provides both textual and time-based information, making it suitable for exploring multiple analytical approaches.

## Project 1: Natural Language Processing (NLP)

### Business Problem

The client needs an efficient way to understand large volumes of customer feedback and identify the topics customers frequently discuss

Manually reviewing individual comments can be time-consuming. NLP techniques can help transform unstructured text into useful information for customer support and product improvement

### Approach

- Load and inspect the customer reviews dataset
- Clean and preprocess review text
- Perform tokenization and remove unnecessary text elements
- Preserve important negation words to retain contextual meaning
- Apply lemmatization
- Analyze frequent words using unigram frequency analysis
- Extract and examine common bigrams

### Key Findings

- Customer ratings are heavily concentrated around five-star reviews
- Frequently occurring terms include `nook`, `not`, `book`, `kindle`, and `screen`
- Common product-related bigrams include `battery life`, `touch screen`, and `sd card`
- Customer discussions highlight product functionality, screen usability, and storage capabilities

### Business Recommendations

Businesses can use text analytics to identify commonly discussed product features and prioritize areas requiring further investigation. Combining word frequency analysis with sentiment analysis could provide a deeper understanding of customer satisfaction and dissatisfaction

## Project 2: Time Series Analysis

### Business Problem

The client wants to understand how customer feedback changes over time, identify periods of increased review activity, and monitor changes in customer satisfaction

### Approach

- Convert review timestamps into datetime format
- Handle invalid or missing timestamps
- Sort observations chronologically
- Resample review data into monthly intervals
- Calculate monthly review volumes
- Calculate monthly average customer ratings
- Apply a three-month rolling average to smooth short-term fluctuations
- Visualize review activity and rating trends

### Key Findings

- Review activity increased considerably after 2010
- The highest review volumes occurred during 2013–2014
- Average customer ratings generally remained favorable, frequently ranging between 3.5 and 4.5 stars during the more active period
- The three-month rolling average helped reveal broader rating patterns
- Earlier periods contained limited observations, making long-term comparisons less reliable

### Business Recommendations

Organizations can monitor monthly review volumes and average ratings to identify changes in customer engagement and satisfaction

Rolling averages can help distinguish short-term fluctuations from more persistent changes that may require business attention

**Note:** This project focuses on historical time series analysis and trend monitoring rather than building a future forecasting model

## Project 3: Neural Network Modeling

### Business Problem

The client wants to explore whether deep learning can automatically classify customer reviews according to their numerical ratings

An automated classification system could help businesses process customer feedback more efficiently and identify potential dissatisfaction

### Approach

- Prepare review text and numerical rating labels
- Split the dataset into training and testing sets
- Apply TF-IDF vectorization to transform text into numerical features
- Build a Multilayer Perceptron (MLP) neural network
- Use ReLU activation functions in the hidden layers
- Apply a softmax output layer for five-class classification
- Introduce dropout regularization and early stopping
- Evaluate the model using accuracy, classification reports, and a confusion matrix

### Model Architecture

The neural network consists of:

- Input layer: 2,000 TF-IDF features
- First hidden layer: 128 neurons with ReLU activation
- Dropout layer: 30% dropout rate
- Second hidden layer: 64 neurons with ReLU activation
- Output layer: 5 neurons with softmax activation

### Key Findings

- The model achieved approximately 58% test accuracy
- The macro F1-score was approximately 0.20
- Training accuracy reached approximately 100%, while validation accuracy declined to approximately 53.1%
- The confusion matrix revealed difficulty identifying minority rating categories, particularly two-star and three-star reviews
- The model showed a strong tendency to predict five  star ratings

### Business Recommendations

The model is not suitable for deployment in its current state because its predictions are unreliable across rating categories

Potential improvements include:

- Applying class weights to address class imbalance
- Increasing the size and diversity of the training dataset
- Reducing model complexity
- Comparing neural network performance against traditional machine learning classifiers such as Logistic Regression
- Evaluating class-specific precision, recall, and F1-scores

## Technologies and Tools

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Data Manipulation | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| NLP | NLTK |
| Text Feature Extraction | TF-IDF |
| Machine Learning | Scikit-learn |
| Deep Learning | TensorFlow, Keras |
| Development Environment | Jupyter Notebook |
| Version Control | Git and GitHub |

## Key Learning Outcomes

Through these projects, the following data science concepts were explored:

- Text preprocessing and feature extraction
- Exploratory data analysis and data visualization
- Working with datetime data and temporal aggregation
- Understanding trends and rolling averages
- Transforming unstructured text into numerical representations
- Building and evaluating neural network models
- Understanding class imbalance and overfitting
- Translating model results into business recommendations

## Conclusion

These three projects demonstrate how different data science techniques can address distinct business challenges

The NLP analysis provides insights into customer discussions, time series analysis reveals changes in review activity and satisfaction over time, and neural network modeling demonstrates the potential and limitations of automated review classification

An important lesson from this work is that successful data science involves more than building models. Understanding the data, selecting appropriate techniques, evaluating results critically, and communicating actionable findings are equally important

---
