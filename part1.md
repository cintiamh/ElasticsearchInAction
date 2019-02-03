# Part 1

What Elasticsearch can do for you in terms of functionality.

1. [Introducing Elasticsearch](#introducing-elasticsearch)

# Introducing Elasticsearch

Search:
* return relevant search results,
* return statistics,
* do all quickly.

Built on top of Apache Lucene.

## Solving search problems with Elasticsearch

### Providing quick searches

* *Index* is a data structure which you create along with your data and which is meant to allow faster searches.

Lucene does *inverted indexing*:

Raw data:
-------------------------------
Blog Post ID | Tags
-------------------------------
1            | elections
2            | peace
3            | elections, peace
4            | peace
-------------------------------

Index data:
-------------------------
Tags      | Blog Post IDs
-------------------------
elections | 1, 3
peace     | 2, 3, 4
-------------------------

The tradeoff for improved search performance and relevancy is that the index will take up disk space and adding new blog posts will be slower because you have to update the index after adding the data itself. On the upside, tuning can make Elasticsearch faster, both when it comes to indexing and searching.

### Ensuring relevant results

* *Relevancy score* is a number assigned to each document that matches your search criteria and indicates how relevant the given document is to the criteria.
* *TF-IDF* (term frequency-inverse document frequency) algorithm used to calculate a document's relevancy by default. Two factors:
  * *Term frequency* the more times the words you're looking for appear in a document, the higher the score.
  * *Inverse document frequency* the weight of each word is higher if the word is uncommon across other documents.

Example: if you are looking for "bicycle race" on a cyclist's blog, the word "bicycle" counts much less for the score than "race". But the more times both words appear in a document, the higher that document's score.

### Searching beyond exact matches

* *typos*: you can configure Elasticserach to be tolerant of variations (fuzzy queries).
* *derivatives*: you can use analysis, to make Elasticsearch understand related words: "bicycle", "bicyclist", "cycling".
* *use statistics*: present statistics through aggregations, which is a way to get counters from the results of your query, to find groups, categories, etc.
* *providing suggestions*: you can use suggestions to predict their searches as they type. You can also show popular results as they type.

## Exploring typical Elasticsearch use cases

### Using Elasticsearch as the primary back end

Elasticsearch is a modern search engine that provide durable storage, statistics, and many other features you've come to expect from a data store.

If you are starting a new project, we recommend that you consider using Elasticsearch as the only data store to help keep your design as simple as possible.
