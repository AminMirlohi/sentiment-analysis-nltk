# Sentiment Analysis using NLTK

This repository contains code to perform sentiment analysis using the Natural Language Toolkit (NLTK) library in Python. The sentiment analysis is done using two approaches: SentiWordNet and Opinion Lexicon.

## Installation

To run this code, you need to have Python installed on your system. You also need to install the NLTK library and download the necessary datasets. 

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the required packages.

```bash
pip install nltk
```

After installing the NLTK library, you need to download the required datasets. Open a Python terminal and run the following commands:

```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')
nltk.download('sentiwordnet')
nltk.download('opinion_lexicon')
```

## Usage

1. Clone the repository to your local machine:

```bash
git clone https://github.com/username/sentiment-analysis.git
```

2. Navigate to the cloned repository:

```bash
cd sentiment-analysis
```

3. Run the Python script:

```bash
python sentiment_analysis.py
```

## Code Explanation

### Importing Packages

The first part of the code imports the necessary packages and libraries. These include:
- `nltk`: The NLTK library for natural language processing.
- `pandas`: Used for handling data in tabular format.
- `numpy`: Required for numerical operations.
- `seaborn` and `matplotlib`: Used for data visualization.
- `ndjson`: Used for reading and writing NDJSON (Newline Delimited JSON) files.
- `confusion_matrix` from `sklearn.metrics`: Used to calculate the confusion matrix.

### Sentiment Analysis Functions

The code includes two main functions for sentiment analysis:
1. `getSentimentScore(text)`: This function calculates the sentiment score for a given text using SentiWordNet. It breaks the text into sentences, processes each sentence to remove punctuation and convert it to lowercase, and then calculates the sentiment score based on the SentiWordNet scores of the words in the sentence.
2. `getSentimentScoreOplex(text)`: This function calculates the sentiment score for a given text using the Opinion Lexicon from NLTK. It follows a similar process as the previous function, but uses the positive and negative words from the Opinion Lexicon to calculate the sentiment score.

### Reading and Preprocessing Data

The code reads data from a JSON file using the `ndjson` package. It creates a pandas DataFrame to store the reviews. It then drops any rows with missing values in the 'reviewText' column.

### Sentiment Analysis and Evaluation

The code applies the `getSentimentScore()` function to calculate the sentiment score using SentiWordNet for each review in the DataFrame. It then classifies the sentiment as 'positive', 'negative', or 'neutral' based on the score. The true sentiment for each review is determined based on the 'overall' rating provided. The predicted and true sentiments are stored in separate lists.

The code also applies the `getSentimentScoreOplex()` function to calculate the sentiment score using the Opinion Lexicon for each review. It classifies the sentiment and stores it in a separate column in the DataFrame.

### Evaluation Metrics

The code calculates the confusion matrix using the true and predicted sentiments obtained from both approaches. It then uses seaborn and matplotlib to plot the confusion matrix as a heatmap.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

