# Tech News Recommendation

This project focuses on analyzing Technews articles from a variety of reliable sources to identify important trends and provide recommendations for related articles. 
The objective is to help users discover relevant articles based on patterns in the data rather than relying on just popular or platform-specific recommendations. 

---

## Project Overview

Especially for tech news, it is not easy to understand what's being explained right away just reading one article. So we often look for related articles. However, with so much information available online, it’s not always easy to find the most relevant content. Even if there is, news sites only provide articles limited to their site. We don't know if it's a recommendation for advertising or for commercial use.

The Tech News Project aims to solve this problem by processing technology-related news articles by
+ Analyzing trends over time to identify dominant and emerging themes.
+ Categorizing articles into detailed subcategories like AI, quantum computing, and cybersecurity.
+ Recommending related articles based on their content using efficient methods like Locality-Sensitive Hashing (LSH).
The project implemented in a web application too to showcases outputs.

---

## Setup and Prerequisites

**1. Data Requirement:**
+ Ensure the cleaned_combined_data.csv file is available. It should contain columns like Title, Content, Publication Date, URL, and Author.
  If you want to use other dataset, keep in mind that you have to modify our code or dataset to fit in this code.

**2. Required Environment:**
+ Use Python 3.12 or above.
+ Install required libraries (listed in the Dependencies section).
  ```pip install pandas numpy matplotlib seaborn plotly scikit-learn datasketch dash jupyter-dash dash-bootstrap-components```

**3. Run Instructions:**
+ Execute the codes sequentially for trend analysis, clustering, and recommendations.
+ Run the Dash web application using the provided script.
  
---

## Features

**Part 1: Scarping & Crawling**

Collect data(articles) to make a dataset. Beware of follow corresponding sites robot.txt or policy.

**Part 2: Data Preparation**

Cleans and preprocesses text data for further analysis to reduce noise.

**Part 3: Clustering**

Categorize articles into meaningful clusters.

**Steps:**

- Apply TF-IDF vectorization to textdata.
- Reduce dimensions using PCA.
- Perform hierarchical clustering to identify initial cluster centroids which is used in K-means.
- Finalize clusters using K-means clustering.

**Output:** Cluster labels based on top keywords.

**Part 4: Locality-Sensitive Hashing (LSH)**

Efficiently find and recommend similar articles within the same cluster.

**Steps:**

- Use MinHash to generate MinHash signatures.
- Create a Locality-Sensitive Hashing index to store MinHash signatures.
- Query LSH index with MinHash signatures of given article.

**Output:** Return similar document.

**Part 5: User Application**

Provide a user-friendly interface for visualizing trend and article recommendations.

**Features:**

- Trends Page: Displays keyword trends using the Trends.png plot.
- Recommendation Page:
    1. Input a URL to find similar articles.
    2. Display top recommendations with clickable links.

**Part 6: Data Properties**

Explore basic properties of the dataset.

**Output:** Statistical summaries of the dataset.
