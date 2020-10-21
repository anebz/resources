# Chapter 8: Lexical acquisition

Lexical acquisition: develop algorithms and statistical techniques that fill the holes in existing machine-readable dictionaries by looking at the occurrence patterns of words in large text corpora.

We constantly invent new words and new uses of old words. Even if we could compile a dictionary that completely covers today's language, it would inevitable become incomplete in a matter of months. That's why lexical acquisition is important.

Lexicon: the part of the grammar/language that includes the lexical entries for all the words and/or morphemes in the language and which might also include various other information, depending on the particular theory of grammar.

One important task of lexical acquisition is to augment traditional dictionaries with quantitative information. Four problems are covered in this chapter:

1. Verb subcategorization: the syntactic means by which verbs express their arguments
2. Attachment ambiguity
3. Selectional preferences: semantic categorization of a verb's arguments: thigs that get eaten are usually food items
4. Semantic similarity between words

## 8.1. Evaluation measures

Precision, recall, F1-score. More on p268...

## 8.2. Verb subcategorization

Verbs subcategorize for different syntactic categories, they express their semantic arguments with different syntactic means. 

One category is made up of a set of semantic arguments, and it has several subcategories that express these semantic arguments using different syntactic means. Most dictionaries don't contain information on subcategorization frames.

More on Lerner's and Manning's work on p273:277

## 8.3. Attachment ambiguity

Another problem in parsing natural language is resolving Attachment ambiguities.

Hindle and Rooth, p280-284.

## 8.4. Selectional preferences

Most verbs prefer augments of a particular type: selectional preferences or selectional restrictions. Objects of the verb 'eat' tend to be food items, the subjects of 'think' tend to be people. This is useful when learning new words like 'durian', if it's close to the word 'eat', we can infer that it's a type of food.

## 8.5. Semantic similarity

The most important quest of NLP is the acquisition of meaning. How to represent meaning in a awy that can be operationally used by an automatic system is a largely unsolved problem. Semantic similarity refers to the notion that two words are from the same semantic domain or topic.

### 8.5.1. Vector space models

Vectors in a document space, each entry a_ij contains the number of times the word *j* occurs in document *i*. 

Word space: each entry b_i contains the number of times word *j* co-occurs with word *i*. 

Modified space: nouns, interpreted as head of noun phrases, are the new vectors in this space. Entry c_ij contains the number of times that the head *j* is modified by modifier *i*

Similarity measures:

* Matching coefficient: counts \# dimensions on which both vectors are non-zero. doesn't consider the length of vectors
* Dice coefficient: normalizes for length by dividing by the total number of non-zero entries
* Jaccard coefficient: penalizes a small number of shared entries more than the Dice coefficient
* Overlap coefficient: measure of inclusion, it has a value of 1.0 if every dimension with a non-zero value for the first vector is also non-zero for the second vector
* Cosine: identical to the Dice coefficient with vectors with same number of non-zero entries, but penalizes less in cases where the number of non-zero entries is very different.

The problem with vector space based measure is that they operate (except for cosine, which assumes an Euclidean space), on binary data. But Euclidean space isn't good for probability or count vectors. The question of semantic similarity can be recast as a question of the (dis-)similarity of two probability distributions.

## 8.6. The role of lexical acquisition in NLP

"One cannot learn a new language by reading a bilingual dictionary" Mercer, 1993.

Natural language is in a constant state of flux, adapting to the changing world by creating names and words to refer to new things, new people and new concepts.