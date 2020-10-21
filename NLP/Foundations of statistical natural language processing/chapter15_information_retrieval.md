# Chapter 15: Information retrieval

Algorithms to retrieve information from document repositories, in particular textual information. 

## 15.1. Background on IR

The classical problem in IR is ad-hoc retrieval problem. The user enters a query describing the desired information and the system retrieves a list of documents. 2 main models:

* exact match: returns documents that precisely satisfy some structured query expression, such as boolean queries
* for large and heterogeneous document collections, the result sets of exact match systems are either empty or huge, so newer systems rank documents according to their estimated relevance to the query. 

In ad-hoc, the users can improve the original formulation of a query interactively, by way of relevance feedback: how results from several text databases can be merged into one result list (database merging), which models are appropriate for partially corrupt data (OCRed documents), etc. 

Some IR subfields rely on a training corpus of documents that have been classified as either relevant or non-relevant to a particular query. In text categorization, one attempts to assign documents to two or more predefined categories. 

### 15.1.1. Common design features of IR systems

Most IR systems have as their primary data structure an inverted index, a data structure that lists for each word in the collection all documents that contain it (the postings) and the frequency of occurrence in each document. It makes it easy to search for 'hits'. 

A more sophisticated version of an inverted index also contains positive information. Instead of just listing the documents that a word occurs in, the position of all occurrences in the document are listed as well. It's also possible to search for phrases. If we're looking for 'car insurance', we simultaneously work through the entries for car and insurance int he inverted index. First we intersect the two sets so that we only have docs in which both words would occur, then we look at the position information and keep only those hits for which the position information indicates that 'insurance' occurs immediately after 'car'. 

### 15.1.2. Evaluation 

The quality of many IR systems depends on how well they manage to rank relevant documents before non-relevant ones. One measure is precision at a particular cutoff, or uninterpreted average precision, interpolation, etc.  

### 15.1.3. The probability ranking principle (PRP)

Ranking documents in order of decreasing probability of relevance is optimal

## 15.2. The vector space model

One of the most widely used for ad-hoc retrieval. Rather than considering the magnitude of the vectors, closeness is often calculated by looking at the angles and choosing documents that enclose the smallest angle with the query vector.

### 15.2.1. Vector similarity

Cosine measure or normalized correlation coefficient

Term weighting, tf-idf, in p 541-544.

## 15.3. Term distribution models

An alternative to tf-idf weighting is to develop a model for the distribution of a word and use this model to characterize its importance for retrieval. Poisson distribution, two-Poisson model, the k mixture, inverse document frequency, residual inverse document frequency, etc. in 545-554.

## 15.4. Latent semantic indexing

A different source of information about terms that can be exploited in information retrieval is co-occurrence, the fact that 2+ terms occur in the same documents more often than chance. LSI is a technique that projects queries and documents into a space with 'latent' semantic dimensions. Co-occurring terms are projected onto the same dimensions, non co-occurring ones are projected onto different dimensions. It's based on dimensionality reduction, and it's closely related to principal component analysis. 

Least squared methods, singular value decomposition, etc. in 555-566.

## 15.5. Discourse segmentation

Text collections are increasingly heterogeneous, and an important aspect of heterogeneity is length, which can be incredibly small or huge. 

### 15.5.1. TextTiling

The idea behind this algorithm is to search for parts of a text where the vocabulary shifts from one subtopic to another, these points are then interpreted as the boundaries of multi-paragraph units. Sentence length can vary considerably, the text is therefore first divided into small fixed size units, the token sequences. More about cohesion scorer, depth scorer, boundary selector and the TextTiling algorithm in p 567-570.

