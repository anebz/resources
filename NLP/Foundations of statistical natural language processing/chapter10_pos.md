# 10. Part-of-Speech Tagging

Make sense of language without requiring complete understanding. Tagging is the task of labelling/tagging each word in a sentence with its appropriate part of speech. These tags generally follow the Brown/Penn tag sets. In tagging, we try to determine which of these syntactic categories is the most likely for a particular use of a word in a sentence.

## 10.1. The information sources in tagging

Two sources of information:

1. look at the tags of other words in the context of the word we're interested in. These words may be ambiguous, but the essential observation is that some part of speech sequences are common, AT JJ NN, while others are very unlikely/impossible, AT JJ VBP. This type of syntagmatic structural information is the most obvious source of information, but not very successful. Many content words in English can have various parts of speech.
2. Just knowing the word involved gives a lot of information about the correct tag. This uses the lexical information, which is very important because the distribution of a word's usages across different parts of speech is typically extremely uneven.

## 10.2. Markov model taggers

We look at the sequence of tags in a text as a Markov chain. We assume that a word's tag only depends on the previous tag (limited horizon) and its dependency doesn't change over time (time invariance). 

Markov model formulas in p345-349. Viterbi algorithm p349-351.

## 10.3. Hidden Markov model taggers

Markov model taggers work well when we have a large tagged training set, which is not always the case. If there's no training data, we can use an HMM to learn the regularities of tag sequences. More formulas in p.357-361.

## 10.4. Transformation-based learning of tags

Markov assumptions are too crude for many properties of natural language syntax, why not more sophisticated models? We can condition tags on preceding words (not just preceding tags), or use more context than trigram taggers. Four-gram or bigger n-grams is not feasible because of the large number of parameters we would need.

Transformation-based tagging exploits a wider range of lexical and syntactic regularities. 

More about transformations, learning algorithm, finite state automata. in p363-368.

## 10.6. Applications of tagging

Most applications require an additional step of processing after tagging, partial parsing. This can refer to various levels of detail of syntactic analysis, the simplest of which are limited to finding the noun phrases of a sentence, and more sophisticated approaches assign grammatical functions to NPs and give partial information on attachments.

Another application is information extraction (or message understanding, data extraction, text data mining). The goal is to find values for the predefined slots of a template. Tagging and partial parsing help identify the entities that serve as slots fillers and the relationships between them. Information extraction can be thought of as tagging, except that tags are semantic categories and not grammatical parts of speech.

Another application is question answering systems, which try to answer a user query formulated in natural language (as a question) and return an appropriate noun phrase such as a location, person, or a date.
