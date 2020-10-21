# Chapter 4: Corpus-based work

Main requirements for statistical NLP: computers, corpora and software. (note: most of these resources are outdated, the book was written in 1999). 

## 4.2. Looking at text

### 4.2.1. Low-level formatting issues

* Junk formatting/content
* Uppercase and lowercase

### 4.2.2. Tokenization

Divide the input text into units called tokens where each is either a word or something else like a number or a punctuation mark.

Word can be phonological words vs syntactic words. Graphic word: a string of contiguous alphanumeric characters with space on either side; may include hyphens and apostrophes, but no other punctuation marks. problem with numbers and monetary amounts. 

* Periods: etc., Calif., periods are part of the word
* Hyphens: e-mail, co-operate, pro-Arab, once-quiet, text-based, 26-year-old

Problems:


* Word segmentation in other languages: Chinese, Japanese, Thai, ... don't put spaces in between words at all. Word segmentation is much harder
* Whitespace not indicating a word break: database, data base, phone numbers, New York, phrasal verbs: make up, work out

### 4.2.3. Morphology

sit, sits, sat: separate, collapsed?

Stemming/lemmatization: grouping such forms together and working in terms of lexemes. one tries to find the lemma/lexeme of which one is looking at an inflected form.


### 4.2.4. Sentences

What is a sentence? Something ending with a '.', '?' or a '!'. 90% of periods are sentence boundary indicators. Mr.? Sentences are on average around 23 words long.


## 4.3. Marked-up data

### 4.3.1. Markup schemes

* SGML: standard generalized markup language. HTML is an instance of an SGLM encoding. 
* XML: simplified subset of SGML, designed for web applications

### 4.3.2. Grammatical tagging

Brown tags (used in Chapter 3 Linguistics Essentials). A tag set encodes both the target feature of classifications, telling the user the useful information about the grammatical class of a word, and the predictive features, encoding features that will be useful in predicting the behaviour of other words in the context.