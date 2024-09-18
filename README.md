# Aspect-Based Sentiment Analysis on Flipkart Reviews

This project focuses on **aspect-based sentiment analysis** of product reviews, particularly those scraped from Flipkart. The goal is to extract key aspects (such as "design", "battery life", "value for money") from customer reviews and determine the sentiment (positive or negative) associated with each aspect. The project includes web scraping, data preprocessing, sentiment classification, and aspect extraction using LDA (Latent Dirichlet Allocation).

## Project Overview

In this project, we:
1. Scrape product reviews from **Flipkart** for various products (e.g., headphones).
2. Perform comprehensive text preprocessing to clean and prepare the data.
3. Use **Logistic Regression** and **Naive Bayes** to classify reviews into spam/legitimate categories and to conduct sentiment analysis.
4. Apply **LDA (Latent Dirichlet Allocation)** to identify important aspects of the product from the reviews.
5. Perform **Aspect-Based Sentiment Analysis** on custom input reviews to evaluate different aspects of the product.

### Note:
- This project was completed in **2022**, and Flipkart may have updated their site structure since then. As a result, the **web scraping code** might need modifications to adapt to the current site layout.
- Alternatively, you can bring your own **custom dataset** of product reviews to use for analysis.

## Key Features

1. **Web Scraping**: 
   - We use BeautifulSoup to scrape product reviews from Flipkart, collecting details like product ratings, review text, upvotes/downvotes, and more.
   - The scraped data is stored in a CSV file and used for further analysis.
   
. **Spam Detection**: 
   - A spam detection model is trained using a **[Labelled Yelp Dataset](https://www.kaggle.com/datasets/abidmeeraj/yelp-labelled-dataset)**.
   - The model is applied to the scraped Flipkart reviews to filter out potential spam reviews.


3. **Text Preprocessing**:
   - The text is cleaned by removing URLs, emojis, special characters, and non-standard characters.
   - Tokenization, stopword removal, stemming/lemmatization are performed to prepare the data for model training.

4. **Sentiment Analysis**:
   - **Naive Bayes** and **Logistic Regression** models are trained to classify the sentiment of reviews (positive or negative).
   - Sentiment is determined based on the overall rating and textual features of the review.

5. **Aspect-Based Sentiment Analysis**:
   - **LDA (Latent Dirichlet Allocation)** is used to identify important aspects (topics) from the reviews, such as "design", "battery life", and "value for money".
   - Sentiment for each aspect is analyzed and the overall sentiment of the review is determined.
   - Custom input reviews can be analyzed to extract sentiments related to specific aspects.

## Project Files

- **flipkart_reviews_scraping.ipynb**:
   - Code for scraping reviews from Flipkart.
   - This code may need updates if Flipkart has changed its site structure since 2022. Alternatively, you can provide your own review dataset for analysis.
   
- **WM_PROJECT_FINAL.ipynb**:
   - Contains the complete workflow for data preprocessing, sentiment analysis, and aspect-based sentiment analysis.
   - Includes steps for text cleaning, spam detection, review classification, and aspect extraction using LDA.

## Installation and Setup

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/aspect-based-sentiment-analysis.git
    ```

2. **Dataset**:
   - Use the provided scraping script (`flipkart_reviews_scraping.ipynb`) to create a dataset of reviews from Flipkart, or bring your own dataset of reviews.
   - Example of a dataset structure:
     - `product_id`: Unique product identifier.
     - `review`: Review text.
     - `rating`: Rating given by the customer.

3. **Run the Jupyter Notebooks**:
   - Use `WM_PROJECT_FINAL.ipynb` to preprocess the data, train the sentiment analysis model, and perform aspect-based sentiment analysis.

## How to Use

1. **Web Scraping**:
   - Modify the `SEARCH_QUERY` and `TOP_N_PRODUCTS` constants in the scraping script to fetch reviews for specific products (e.g., "headphones").
   - Run the scraping script to collect reviews and save them in a CSV file.

2. **Data Preprocessing and Sentiment Analysis**:
   - Load the scraped dataset or your custom dataset into `WM_PROJECT_FINAL.ipynb`.
   - Preprocess the reviews (cleaning, tokenizing, lemmatizing).
   - Train the sentiment analysis models using the preprocessed data.

3. **Aspect-Based Sentiment Analysis**:
   - Use the pre-trained LDA model to identify key aspects from the reviews.
   - Analyze the sentiment of each aspect for custom input reviews.

## Example

Here’s how you can analyze the sentiment of a custom review:

```python
text = "The battery life is great, but the design feels cheap."
aspect_sentiment_analysis(text, clf, vectorizer, lda_model, lda_topics)
