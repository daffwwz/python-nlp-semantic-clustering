# Natural Language Processing for Analyzing The Most Frequent Graduate Admission Interview Questions
## Background
My gf just told me she will have a graduate admission interview for her master's degree soon (yay).

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

## Most Frequently Asked Interview Questions

Below are the standardized (canonical) interview questions extracted via clustering, ranked by frequency.  
Each item represents one semantic cluster and shows how often similar questions appeared based on KMeans clustering with `random_state=42` for reproducability.

| Rank | Representative Question | Frequency |
|-----:|--------------------------|----------:|
| 1 | **What is your most significant accomplishment?** | 19 |
| 2 | **How will you contribute to our program?** | 19 |
| 3 | **Why are you interested in this degree?** | 18 |
| 4 | **What are your career goals?** | 17 |
| 5 | **What are your research interests?** | 16 |
| 6 | **What courses have you enjoyed the most throughout your college career?** | 15 |
| 7 | **What are your strengths and weaknesses?** | 11 |
| 8 | **Tell me how you handle stress.** | 11 |
| 9 | **Why did you choose this school?** | 10 |
| 10 | **How do you feel your undergraduate studies have prepared you for this program?** | 10 |
| 11 | **Tell me about yourself.** | 8 |
| 12 | **What would you change about yourself and why?** | 7 |
| 13 | **Why do you think this program is a good fit for you?** | 6 |
| 14 | **What have you been reading recently?** | 5 |
| 15 | **What questions do you have for me?** | 4 |

## Note
The representation and clustering still to general, better vary the n_clusters or use another method for comparison.
