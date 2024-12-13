Goal: Perform sentiment analysis on YouTube comments and create a UI to compute the positive-to-negative comment ratio from a YouTube video link.

Sentiment Score Breakdown
Negative: -1 to < 0

Neutral: 0

Positive: > 0 to 1

Workflow

Run the following files in sequence:

comments.ipynb: Collect comments using the YouTube API.

engineering.ipynb: Preprocess data for sentiment analysis.

pipeline.py: Manage daily feature updates.

pipene.py: Handle predictions for new data.

app.py: Deploy the user interface.


Setting up the YouTube API

Log into your Google account.

Go to Google Cloud Console.

Create a new project.

Search for and enable YouTube Data API v3.

Generate API credentials (API Key).

Save the API Key in a .api_key file
> cat .api_key  
KEY=PASTE_VALUE_HERE

Data Labeling with VADER Sentiment Analysis
Library: VADER Sentiment Analysis
Install: PyPI

Dataset
Collected YouTube comments using the YouTube API.
Sentiments labeled using VADER.
Features include comment text and corresponding sentiment labels.

Steps to Execute
1. Data Collection
Use the YouTube API to fetch comments.
Create a function to extract video IDs from YouTube links.
2. Model Training
Train a Random Forest Regressor for sentiment analysis.
Evaluate model performance using:
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
3. Deployment
Deploy models and vectorizers to Hopsworks Model Registry.
Build a Gradio interface for user interaction.

Deployment Interfaces
Gradio
Provides a simple interface to input YouTube links and analyze sentiment.
Huggingface App
Access the sentiment analysis app here.

How to Run

Data Collection

Set up the Google API key for YouTube API.

Configure the .api_key file with:
YouTube API key
Hopsworks API key
Run the data collection scripts.
Model Training & Deployment
Train models using the provided code.
Deploy models and vectorizer to Hopsworks Model Registry.
Gradio Interface
Configure the .api_key file.
Run the Gradio interface script.
Access the interface to analyze sentiments interactively.
Results
Model Performance: Random Forest Regressor achieved promising results with MSE and RMSE evaluations.
User Interaction: The Gradio interface and Huggingface App simplify sentiment analysis for end users.

Conclusion

This project demonstrates a complete pipeline for:

Collecting and labeling YouTube comments.

Training and deploying sentiment analysis models.

Building interactive tools for user sentiment insights.

The solution benefits YouTube content creators and researchers analyzing viewer feedback.
