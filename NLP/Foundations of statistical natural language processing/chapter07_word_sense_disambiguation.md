# Chapter 7: Word sense disambiguation WSD

Many words have several meanings or senses, which creates ambiguity about how they should be interpreted. The task of *disambiguation* is to determine which of the senses of an ambiguous word is invoked in a particular use of the word. This is done by looking at the context.

A word is assumed to have a finite number of discrete senses, often given by a dictionary/thesaurus/other reference, and the task of the program is to make a forced choice between those senses for the meaning of each usage of an ambiguous word, based on its context. Another ambiguity can be when a word is used as different parts of speech (noun, verb), for which tagging is useful. WSD could be regarded as tagging, but using semantic tags instead of part of speech tags.

## 7.1. Methodological preliminaries

### 7.1.1. Supervised and unsupervised learning

### 7.1.2. Pseudowords

In order to test algorithms, s large number of occurrences must be disambiguated by hand --> generate artificial evaluation data for the comparison and improvement of text processing algorithms --> pseudowords

### 7.1.3. Upper and lower bounds on performance

Evaluation needs to determine how well the algorithm performs relative to the difficulty of the task.

* Upper bound: usually human performance, but this depends on the amount of representation of context. If the algorithm looks just at three words on each side of the ambiguous word, even humans wouldn't perform very well.
* Lower bound, baseline: performance of the simplest possible algorithm. A baseline should always be given because raw performance numbers make it impossible to assess how hard disambiguation is for a particular word.

These bounds are most relevant when the metric is accuracy, but may not be for others.

## 7.2. Supervised disambiguation

### 7.2.1. Bayesian classification

The algorithm looks around an ambiguous word in a large context window, the classifier does no feature selection, instead it combines the evidence from all features. Formulas in book pages 236 onwards.

* The Bayes decision rule is optimal because it minimizes the probability of error. For each individual case, it chooses the class/sense with the highest conditional probability and hence the smallest error rate.
* Naive Bayes assumption: has 2 consequences
    - all the structure and linear ordering of words within the context is ignored --> bag of words model
    - The presence of one word in the bag is independent of another, which is in reality not true.

### 7.2.2. An information-theoretic approach

The Bayes classifier attempts to use information from all words in the context window to help in the disambiguation decision, at the cost of a somewhat unrealistic independence assumption.

An information-theoretic approach tries to find a single contextual feature that reliably indicates which sense of the ambiguous word is being used. For example, for the verb 'prendre', its object is a good indicator. More on the algorithm in book page 239.

## 7.3. Dictionary-based disambiguation

If we have no information about the sense categorization of specific instances of a word, we can fall back on a general characterization of the senses. These methods rely on definitions of senses in dictionaries or thesauri

### 7.3.1. Disambiguation based on sense definitions

A word's dictionary definitions are likely to be good indicators for the senses they define. More on formulas and algorithm in book page 242+243.

Information of this sort derived from a dictionary is insufficient for high quality WSD. Accuracies reported of 50-70%

### 7.3.2. Thesaurus-based disambiguation

This disambiguation exploits the semantic categorization provided by a thesaurus or a dictionary with subject categories. The semantic categories of the words in a context determine the semantic category of the context as a whole, and this category in turn determines which word senses are used.

A general categorization of words into topics is often inappropriate for a particular domain. More on formulas and algorithm in book page 245.

This method achieves high accuracy when thesaurus categories and senses align well with topics. When a sense is spread out over several topics, the algorithm fails. A topic-based classification doesn't do well on this sense

### 7.3.3. Disambiguation based on translations in a second-language corpus

Book in page 247.

### 7.3.4. One sense per discourse, one sense per collocation

Book in page 249.

## 7.4. Unsupervised disambiguation

Completely unsupervised disambiguation isn't possible if we mean sense tagging, labelling occurrences as belonging to one sense or another. Sense tagging requires that some characterization of the senses be provided. However, sense discrimination can be performed in a completely unsupervised fashion, it's possible to cluster the contexts of an ambiguous word into a number of groups and discriminate between these groups without labelling them. For example, context-group discrimination. More on algorithm and formula in book page 254.

## 7.5. What is a word sense?

The most frequently used methodology is to adopt the sense definition in a dictionary and then ask subjects to label instances in a corpus based on these definitions. But randomly selecting ambiguous words introduces a bias, meaning their figures might not reflect actual inter-judge agreement. More in pages 258+.