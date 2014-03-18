# Web search basics
## Preface

How is web search different from traditional information retrieval?
----------------------------------------------------------------------
## Web is messy

1. Web has decentralized content publishing with no central control of authorship.
2. Web contents have different level of authorities.
3. Web contents have different opinions that may speak contrast views about a topic.
4. Web contents change all the time.

How to evaluate web pages?
----------------------------------------------------------------------
1. Web consists of 1) static HTML pages 2) links between them
2. If page A links to page B, text on the hyperlink from A to B is `anchor text`
3. Two types of links: `in-links` and `out-links`.
4. Distribution of the number of links into a web page follows a `power law`: total number web pages with in-degree i is proportional to 1/i (Zipf's Law)

Spam and Spam detection
----------------------------------------------------------------------
1. Web content creators have commerical motives to gain from manipulating search engine results.
2. Given that spamming is inherently an economically motivated activity, an industry of `Search Engine Optimizers` is born.

Query needs
----------------------------------------------------------------------
1. `Informational`: seek general information on a broad topic (e.x. Best retaurants in NYC)
2. `Navigational`: seek the website or home page of a single entity (e.x. Columbia Univeristy homepage)
3. `Transactional`: a prelude to the user performing a transaction on the Web (e.x. Gifts for Christmas)

General search engine indexing strategy
----------------------------------------------------------------------
1. Impossible to reason about the fraction of the Web indexed by a search engine, because there's infinite number of dynamic web pages.
2. Search engines generally organize their indexes in various in various tiers and partitions, not all of which are examined on every search.

## Compare index size of different search engines
  * `capture-recapture method`: pick a random page from the index of E_1 and test whether it is in E_2; symmetrically, test whether a random page from E_2 is in E_1. Let x be fraction of pages from E_1 that is in E_2, let y be fraction of pages from E_2 that is in E_1.

      |E_1| / |E_2| ~= y / x

  * How to perform search engine comparison:
    1. Look at a search log of web searches, send a random search from this log to E_1 (it needs access to search logs)
    2. Generate a random IP, send a request to a web server residing at the random address (many hosts may share one IP due to virtual hosting)
    3. Random walks: run a random walk starting at an arbitrary web page (web pages are not strongly connected as assumed).
    4. Random queries: use a random conjunctive query on E_1 and pick from the top 100 returned results of a page P at random. We then test p for presence in E_2 by choosing 6-8 low-frequency terms in p and repeating the experiement a large number of times.

## Handle search duplicates
  * Problem: the Web contains multiple copies of the same content. Some deplications are legitimate (e.x. cloned repositories mirrored to provide redundancy)
  * One solution: shingling.
      1. Def: given a positive integer k and a sequence of terms in a document d, the `k-shingle of d` is the set of all consecutive sequences of k terms in d.
      2. Ex: texts "a rose is a rose is a rose". The `4-shingles` for this text are "a rose is a", "rose is a rose", and "is a rose is", note that the set eliminates duplicates.
  * Goal: compare similarity of two docs (A and B)
      1. Reduce A and B to sets of substrings by `k-shingling`
      2. Given substring set S(A) and S(B):
            SIM(A, B) = |S(A) intersect S(B)| / (S(A) union S(B))

Other references
----------------------------------------------------------------------

`Zipf's law`: if t_1 is the most common term in the collection, t_2 is the next most common, and so on, then the collection frequency cf_i of the i_th most common term is proportional to 1/i
