# Artificial-Intelligence-
Sentiment Analysis for Marketing 
# Import necessary libraries
# Import necessary libraries
# Import necessary libraries
# Import necessary libraries
# Import necessary libraries
# Import necessary libraries
# Import necessary libraries
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

# Initialize the VADER sentiment analyzer
nltk.download('vader_lexicon')
sia = SentimentIntensityAnalyzer()

# Sample list of reviews
reviews = [
    "I love this product! It's amazing!",
    "The customer service was terrible.",
    "This is just okay, not great.",
    "I have mixed feelings about it.",
]

# Function to perform sentiment analysis
def analyze_sentiment(text):
    sentiment_score = sia.polarity_scores(text)
    
    # Determine sentiment based on the compound score
    if sentiment_score['compound'] >= 0.05:
        sentiment = 'Positive'
    elif sentiment_score['compound'] <= -0.05:
        sentiment = 'Negative'
    else:
        sentiment = 'Neutral'
    
    # Return sentiment and sentiment scores
    return sentiment, sentiment_score

# Analyze sentiment for each review
for review in reviews:
    sentiment, sentiment_scores = analyze_sentiment(review)
    
    print(f"Review: '{review}'")
    print(f"Sentiment: {sentiment}")
    print("Sentiment Scores:")
    print(f"Positive: {sentiment_scores['pos']}")
    print(f"Neutral: {sentiment_scores['neu']}")
    print(f"Negative: {sentiment_scores['neg']}")
    print(f"Compound: {sentiment_scores['compound']}")
    print("---")
