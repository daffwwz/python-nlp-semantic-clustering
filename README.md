# python-nlp-semantic-clustering

## Main Idea
This repository consisted of python scrapper code to get more than 100+ interview questions, an excel data to contains all the questions, and a python code for analyzing frequently asked interview questions.
First, all of the questions will be converted into embeddings using 'all-MiniLM-L6-v2' model from `SentenceTransformer`. Then the embeddings are clustered using KMeans algorithm. 
The centroid of each clusters is calculated and cosine similarity of each sentence to the centroid is computed to get a representative question of each clusters.
Finally, the representative questions of each cluster is presented with a given information of how many similar questions are there.
