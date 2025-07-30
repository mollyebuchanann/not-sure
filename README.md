# Reddit Subreddit Activity Analysis using Google BigQuery

This project analyzes Reddit comment data from 2014, stored in Google BigQuery, to uncover insights into subreddit popularity and user activity. The data is queried directly using the BigQuery API, processed with `pandas`, and visualized using `matplotlib`.

## Contents

- Load Reddit comment data from Google BigQuery
- Identify most active subreddits based on unique users
- Visualize activity distributions using histograms
- Analyze top 100 subreddits with highest user engagement

##  Technologies & Libraries Used

- Google Cloud BigQuery API (`google.cloud.bigquery`)
- `pandas` for data manipulation
- `numpy` for numeric operations
- `matplotlib` for visualization
- Jupyter Notebook for code execution and analysis

## Key Tasks Performed

###  Data Extraction from BigQuery

- Retrieved Reddit comment data from the public dataset: fh-bigquery.reddit_comments.2014
   Example query used:
  ```sql
SELECT subreddit, COUNT(DISTINCT author) AS active_users
FROM `fh-bigquery.reddit_comments.2014`
WHERE author IS NOT NULL
GROUP BY subreddit


### Visualization
Plotted a histogram to visualize the probability density of subreddit user activity
Used logarithmic scale to handle skew in distribution
Identified and displayed the top 100 subreddits based on active users

### Insights

The distribution of user activity is highly skewed—few subreddits dominate in active participation.
The top 100 subreddits show significant disparity in user base size.
Using COUNT(DISTINCT author) helped focus on unique contributors.

 
### Project Structure

reddit-bigquery-social-analytics/
├── reddit_subreddit_analysis.ipynb
├── README.md
└── requirements.txt (optional)

### Dataset Source

Google BigQuery Public Datasets – Reddit Comments


### ⚙️ Setup

To run this project locally:

Ensure you have a Google Cloud project and BigQuery access.
Authenticate your local environment:
gcloud auth application-default login
Install required Python packages:
pip install google-cloud-bigquery pandas matplotlib
Open the notebook in Jupyter or VS Code and run each cell.

