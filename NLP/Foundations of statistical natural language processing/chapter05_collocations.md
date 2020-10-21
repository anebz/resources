PART II Words

# Chapter 5: Collocations

*Collocation*: expression consisting of 2+ words that correspond to some conventional way of saying things: NP like "strong tea", "weapons of mass destruction", phrasal verbs like "make up", and other stock phrases like "the rich and powerful". 

Collocations are characterized by limited *compositionality*. A natural language expression is compositional if the meaning of the expression can be predicted from the meaning of the parts. Example of non-compositionality: idioms like "kick the bucket".

Approaches to finding collocations: frequency, selection based on mean and variance of the distance between focal word and collocating word, hypothesis testing and mutual information. 

## 5.1. Frequency

Selecting the most frequently occurring bigrams isn't very interesting: of the, in the, to the, on the, for the... But if we pass these most frequent bigrams through a part-of-speech filter (AN(linear function), NN(regression coefficients), AAN(gaussian random variables, ANN), we get more "phrases": new york, united states, los angeles, last year (wrong, it's not a non-compositional phrase), vice president... 

## 5.2. Mean and variance

Many collocations consist of 2 words that stand in a more flexible relationship to one another. "knock door":

* she knocked on his door
* they knocked at the door
* the man knocked at the wooden front door

Words appearing between *knocked* and *door* vary and the distance between the 2 words is not constant so the frequency approach doesn't work. But there is enough regularity in the patterns to determine that *knock* is the right verb to use in this situation and not *hit* or *beat*. 

How to capture bigrams at a distance. Define a collocation window (3-4 on each side of the word) and enter every word pair in these as a collocational bigram.

* *Mean*: average offset = sum of offsets / num. of times 2 words co-occur
* *Variance*: how much the individual offsets deviate from the mean. s2 = sum of (the distance from offset to the mean offset)^2 / (num. of times 2 words co-occur - 1)

## 5.3. Hypothesis testing

High frequency and low variance can be accidental ("new companies"). What we really want to know if two words occur together more often than chance. What is chance? This problem is couched in terms of hypothesis testing. 

H0, null hypothesis, formulates that there is no association between the words beyond chance occurrences. Compute the probability p that the event would occur if H0 were true, and reject H0 if p < 0.05, and retain H0 as possible otherwise.

In this data analysis mode we look at two things at the same time: patterns in the data, and how much data we have seen. Even if there's a remarkable pattern, we'll discard it if we haven't seen enough data to be certain that it couldn't be due to chance.

First of all, formulate a null hypothesis which states what should be true if 2 words don't form a collocation. In the simple case, we assume w1 and w2 to be independent. P(w1w2) = P(w1)\*P(w2).

### 5.3.1. The t test

We need a statistical test which tells how (im-)/probable it is that a certain constellation will occur: t test. It looks at the mean and variance of a sample of measurements, where the null hypothesis is that the sample is drawn from a distribution with mean mu. The test looks at the difference between the observed and expected means, scaled by the variance of the data, and tells us how likely one is to get a sample of that mean and variance assuming that the sample is drawn from a normal distribution with mean mu. (more in the test in the book, p163).


### 5.3.2. Hypothesis testing of differences

The t test can also be used to find which co-occurrence patterns best distinguish between two words. More on this in the book, p167.

### 5.3.3. Pearson's chi-square test

The use of the t test has been criticized because it assumes that probabilities are approximately normally distributed, which is not true in general. Alternatively, we can use the chi-square test. More on this in the book, p169.

### 5.3.4. Likelihood ratios

Another approach to hypothesis testing. More appropriate for sparse data than the chi-square test, and also more interpretable than the chi-square statistic. The Likelihood ratio is a number that tells us how much more likely one hypothesis is than the other. More on this in the book, p.172.

## 5.4. Mutual information

(pointwise) Mutual information between two words x' and y'. How much does one word tell us about the other. This mutual information is not the same as in information theory.

Definition: the amount of information provided by the occurrence of the event represented by [y'] about the occurrence of the event represented by [x'] is defined as I(x', y') = log2(P(y'|x')/P(y')) = log2(P(x'|y')/P(x')).

Example: I(Ayatollah, Ruhollah) = ... = 18.38. The amount of information we have about the occurrence of Ayatollah at position *i* in the corpus increases by 18.38 bits if we are told that Ruhollah occurs at position *i+1*. Equivalently, we can say that the uncertainty is reduced by 18.38 bits.

Problems and alternatives in the book, p180. Sparseness is a particularly difficult problem for mutual information. Among perfectly dependent bigrams, as they get rarer, their mutual information increases. Mutual information is a good measure of independence, but it's a bad measure of dependence.

## 5.5. The notion of collocation

(linguistic subsection)

Collocation definition: a sequence of 2+ consecutive words that has characteristics of a syntactic and semantic unit, and whose exact and unambiguous meaning/connotation can't be derived directly from the meaning/connotation of its components. A phrase can be collocation even if it's not consecutive (knock ... door).

* Non-compositionality: the meaning of the collocation is not a straightforward composition of the meanings of its parts. Either the meaning is completely different from the free combination (kick the bucket), or there's a connotation/added element of meaning that can't be predicted from the part.
* Non-substitutability: we can't substitute other words for the components of a collocation even if, in context, they have the same meaning. (white wine, ¬yellow wine). White wine is yellow-ish.
* Non-modifiability: many collocation can't be freely modified with additional lexical material/grammatical transformations. This applies to idioms.

One way to test whether a combination is a collocation is to translate it into another language. If it can't be done word by word, then it's a collocation. make a decision -> ¬faire une décision (prendre une décision). 

Verbs with little semantic context like make, take and do are called *light verbs*. There's nothing about the meaning of these words that explains why we have to say make a decision instead of take a decision
