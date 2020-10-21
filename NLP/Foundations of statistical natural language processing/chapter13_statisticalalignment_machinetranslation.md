# Chapter 13: Statistical alignment and machine translation

The simplest approach to MT is word for word. but there's no one-to-one correspondence between words in different languages, because of lexical ambiguity for example, word order in different languages, etc.

Languages are structured as:

* Interlingua (knowledge representation) -> knowledge-based translation
    - independent of the way particular languages express meaning
* Semantic representation -> semantic transfer
    - represent the meaning source sentences and then generate the translation from the meaning
* Syntactic parse -> syntactic transfer
    - verb-adverb constructions in one language may not be so in another
* Word string -> word-for-word

Most applications use parallel texts, where the same content is available in several languages. First task is to perform gross large scale alignment, noting which paragraphs or sentences in one language correspond to which paragraphs or sentences in another. Second task is to learn which words tend to be translated by which other words --> acquire a bilingual dictionary from text. 

## 13.1. Text alignment

Goal is to find some group of sentences in one language corresponding in content to some other group of sentences in the other --> bead. Each sentence can occur in only one bead. A problem is that in real texts, there are many cases of crossing dependencies, where the order sentences are changed in the translation. The algorithms presented here (the book is from 1999) aren't able to deal with them. The problem can be divided into alignment problems and correspondence problems.

Lexical methods, signal processing techniques explained in p475-484.

## 13.2. Word alignment

A common use of aligned texts is deriving bilingual dictionaries and terminology databases. First the text alignment is extended to a word alignment, then some criterion such as frequency is used to select aligned pairs for which there's enough evidence to include them in the bilingual dictionary.

One approach to word alignment is based on measures of association (section 5.3.3)

## 13.3. Statistical machine translation

SMT is one of the applications of the noisy channel introduced in section 2.2.4. If we want to translate from French to English, we set up a noisy channel that receives as input an English sentence 'e', transforms it into a French sentence 'f', and sends the French sentence 'f' to a decoder. The decoder determines the english sentence 'ê' that 'f' is most likely to have arisen from. We also have to estimate the parameters of the model, the translation probabilities.

* Language model: gives the probability P(e) of the English sentence. We know how to build language models based on n-grams (chapter 6) or probabilistic models (chapter 11 and 12).
* Translation model: gives P(f|e), for example P('Jean aime Marie'|'John loves Mary')
* Decoder: we saw examples in section 2.2.4
* Translation probabilities: they're estimated using the EM algorithm (section 14.2.2). EM is based on solving the credit assignment problem. If a word in the source is strongly aligned with a word in the target, then it's not available anymore to be aligned with other words in the target. This avoids cases of double and triple alignment on the one hand, and an excessive number of unaligned words on the other. 

Implausible models are penalized, if an en word at the beginning of the en sentence is aligned with a french word at the end of the french sentence, this **distortion** decreases the probability of the alignment.

Each en word has a certain **fertility**, which tells how many french words it usually generates. We can capture the tendency of word alignments to be one-to-one and one-to-two. 

* Fertility is asymmetric, often one french word corresponds to several english words
* Independence assumptions: the model gives an unfair advantage to short sentences because fewer probabilities are multiplied
* Sensitivity to training data: small changes in model or traindata can cause large changes in the estimates of the parameters
* Efficiency: sentences of 30+ words take too long

Other problems:

* No notion of phrases: the model relates only individual words
* Non-local dependencies: hard to capture with 'local' models like n-gram models
* Morphology: morphologically related words are treated as separate symbols
* Sparse data problems: estimate for rare words are unreliable
