Information Retrieval Notes
---------------------------------------------

# Fundamental Information Retrieval
=============================================
## Boolean Retrieval
[Chapter 1 of Introduction of Information Retrieval](http://nlp.stanford.edu/IR-book/)

## Index Construction
  - Block merge index construction (Pseudocode)
  - Distributed indexing (What is the idea)
  - Dynamic indexing (What is the idea, what is the problem)
  - Inverted File Search(Paper)

## Vector space scoring
  - Top-K query results
    * Def: find the K docs in the corpus "nearest" to the query q.
    * How to measure "nearest": cosine of query `q` and doc `d`
    * Basic scoring algorithm
    * What is the problem?

  - Inexact top-K query (Why inexact?)
    * Google's original PageRank algorithm
    * Champion lists (Fancy lists)

  - Static quality scores
    * Idea: top-ranking documents to be both relevant and authoritative
    * Modeling authority: assign a query-independent `quality score` in [0,1]
    * net-score(q,d) = g(d) + cosine(q,d)

  - Champion lists in g(d)-ordering

  - High and low lists

  - Impact-ordered postings
    * Why?
    * How is it related to other scoring methods?
    * Early termination
    * idf-ordered terms

  - Parametric and zone indexes
    * Why? A doc has multiple parts, some with special `metadata`, such as Author, Title, Date of publication, Language, Format...

# Web Search
==============================================





