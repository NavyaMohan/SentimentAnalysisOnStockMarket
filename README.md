# SentimentAnalysisOnStockMarket
Sentiment analysis on micro-blogging website(reddit) to determine trending stocks and the sentiment associated with them to aid stock market decision making.

## Excecutive Summary
In this digital era, user generated content is at its all time high.The enormous content, opinions and ideas impact decision making at multiple levels. Text mining/Sentiment analysis is a hot topic and using it for deriving insights on the stock market decisions can be very useful. The idea was from the recent GameStop story. It was interesting to note how a group of likeminded reddit users could control the stock gains of a declining business model. It is interesting to note how opinions and sentiments over a topic in a virtual world translated to a huge change in a real world scenario.This project mainly focuses on determining the Stocks(ticker symbol) that are trending and the Reddit users sentiment towards it. A data pipeline was designed that handles both historical and current posts. The end result is a dashboard with up-to-date information, targeting to help the stock market savvy folks to better decide on what stocks to research more about before investing.

## Approach

● Work with APIs to extract data from Reddit.
● Load the data into Google Cloud Storage (GCS) and use it as point of Ingestion for batch
data
● Write cloud functions to detect file creation and the file metadata to pubsub.
● Publish data from multiple subreddits to Pub/Sub to use it as a point of Ingestion for
streaming data.
● From the above mentioned storages, pull the data, clean the data if required and use it
for batch and stream processing using Data flow.
● Perform sentiment analysis on the datasets (using Google Natural Language API) and
store the final result in the Big Query tables.
● Temporary and staging buckets may be used to store intermediate data and processing
information.
● The final data stored in the Big Query is used for visualization. Charts and graphs will be
plotted using Google Data Studio.

<img width="962" alt="Screen Shot 2023-01-11 at 11 58 49 AM" src="https://user-images.githubusercontent.com/22653266/211905530-a69d2261-ff1e-4b02-bbc1-0372c11d289f.png">

 ## Requirements
1. Basic python programming skills : the entire project uses python for coding
2. Knowledge on Apache Beam
3. Reddit account to pass as a parameter into API calls to scrape data.
4. GCP account with billing configured
5. VM with a python virtual environment to run all the scripts.
6. Dataflow beam instance required at development stage
7. Google Natural Language API enabled

## Data Visualization (Google Data Studio)

<img width="967" alt="Screen Shot 2023-01-11 at 12 04 05 PM" src="https://user-images.githubusercontent.com/22653266/211906537-8d74c284-ee5f-4767-b9e0-81d6dd816b57.png">


