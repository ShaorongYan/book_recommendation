# Recommendating books based on your tweets

This is something @stephanie_davis and I created for the a Hackathon when we were doing our Summer Intern at TapAd. We built a prototype for a book recommendataion system for the company's book club. 

The basic idea is to build a model that can infer your personal interests based on some text-based data about you, and then recommend books based on your personal interests. Here we are using tweets as a showcase because it is an easily acquirable public data. Information about books are extracted from the Goodreads API. 

The workflow is as follows: 
  1. Information extraction from tweets:
    1a. Perform topic modeling for the tweets. 
    1b. Get word embeddings for the top words in each topic.
    1c. Calculate topic embedding by averaging word embeddings.
  2. Information extraction from Goodreads:
    2a. Perform topic modeling for the book info (tags and book description). 
    2b. Get word embeddings for the top words in each topic.
    2c. Calculate topic embedding by averaging word embeddings.
    2d. Get the loadings on topics for each book. 
  3. Calculating distance:
    3a. Calculate the distance between each tweet topic and each of the book topic.
    3b. For each book and each tweet topic, calculate the weighted average based each book's loading on different topics
  4. Rank books by distance and recommend the top k closest books
  
This is just a prototype and many parts can be tweaked, e.g., how are word embeddings aggregated, how are distances aggregated, etc. Feel free to play with it. 
