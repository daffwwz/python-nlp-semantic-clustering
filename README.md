# python-nlp-semantic-clustering

## Project Overview
This repository contains a complete pipeline for collecting, organizing, and analyzing frequently asked interview questions using NLP techniques.
It includes:
1. Python web scrapers to collect 100+ interview questions from multiple sources
2. An Excel dataset containing all scraped questions
3. Python analysis code to cluster and identify frequently asked interview questions

## Methodology
**1. Sentence Embedding**
All interview questions are converted into dense vector representations using the `all-MiniLM-L6-v2` model from the sentence-transformers library.

**2.Clustering**
The sentence embeddings are grouped using the KMeans clustering algorithm, where semantically similar questions are placed in the same cluster.

**3. Representative Question Selection**
- The centroid of each cluster is computed by averaging the embeddings within that cluster.
- Cosine similarity between each question embedding and the cluster centroid is calculated.
- The question with the highest cosine similarity to the centroid is selected as the representative (canonical) question for that cluster.

**4. Frequency Analysis**
Each representative question is presented along with the number of similar questions in its cluster, indicating how frequently that question appears across sources.

