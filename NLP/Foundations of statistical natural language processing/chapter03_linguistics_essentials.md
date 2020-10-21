# Chapter 3: Linguistics essentials

## 3.1. Parts of speech and morphology

* Lexicon: online dictionary where parts of speech for a word are stored
* POS tags: sets of abbreviations for naming these classes. Abbreviations used in the Brown corpus in this week
* Morphological process: formation of the plural (dog-s) from the singular form of the noun (dog). In English a regular verb has 4 distinct forms, irregular verbs 8 forms at most. Types of morphological processes:
    - **Inflection**: systematic modifications of a *root form* by means of *prefixes* and/or *suffixes* to indicate grammatical distinctions like singular and plural. The word class or meaning is not significantly changed, but tense, number plurality are. All the inflectional forms of a word are often grouped as manifestations of a single lexeme.
    - **Derivation**: less systematic, more radical change of syntactic category, often involves change in meaning.
        + wide (extending over a vast area) -> it is wide**ly** believed that... (among a large well-dispersed group of people)
        + soft --> soft**en**
        + understand --> understand**able**
        + teach --> teach**er**
    - **Compounding**: merging of 2+ words into a new word. Even if they are written as separate words, they are pronounced as a single word and denote a single semantic concept. 
        + tea kettle, disk drive, college degree, Spielzeug


### 3.1.1. Nouns and pronouns

*Nouns*: refer to entities in the world like people, animals, things. Ex: dog, tree, person, hat, idea, philosophy

| Type of inflection | Instances |
| ------------------ |:---------:|
| number             | singular, plural |
| gender             | feminine, masculine, neuter | 
| case               | nominative, accusative, dative, genitive | 


*Pronoun*: separate small class of words that act as like variables in that they refer to a person or thing somehow salient in the discourse context.

* *she* refers to the most salient person (of feminine gender) in the context of use, which is Mary
* After *Mary* arrived in the village, *she* looked for a bed-and -breakfast

Forms of pronouns:  
* Nominative/subject case pronouns 
* Accusative/object case pronouns
* Possessive pronouns: *my* car
* Second possessive personal pronoun (special case in English): the object of the preposition *of* describes the possessor: a friend of *mine*
* Reflexive pronouns/anaphors: similar to ordinary/personal pronouns except they always refer to a nearby antecedent in the same sentence, normally the subject
    - Mary saw *herself* in the mirror
        + herself must refer to Mary
    - Mary saw *her* in the mirror
        + *her* cannot refer to Mary

| - | Nominative | Accusative | Possessive | 2nd_Possessive | Reflexive |
|-- |:----------:|:----------:|:--------------:|:---------:|:----------:|
| Tag(s) | PPS | (3SG) | PPO | PP$ | PP$$ | PPL |
| 1SG | I | me | my | mine | myself |
| 2SG | you | you | your | yours | yourself |
| 3SG_masc | he | him | his | his | himself |
| 3SG_fem | she | her | her | hers | herself |
| 3SG_neut | it | it | its | its | itself |
| 1PL | we | us | our | ours | ourselves |
| 2PL | you | you | your | yours | yourselves |
| 3PL | they | them | their | theirs | themselves |

###### Brown tags

* NN: singular noun (candy, woman)
    - NNS: plural nouns
* NNP: proper noun (Alice, Bob)
    - NNPS: plural proper nouns
* NR: adverbial noun (home, west, tomorrow)
    - can be used without modifiers and give information about the circumstances of the event described, like time or location
    - NRS: plural adverbial nouns
* Possessive and genitive extensions (see table above)

### 3.1.2. Determiners and adjectives, words that accompany nouns

* *Determiners* describe the particular reference of a noun.
    - *Articles*: subtype of determiners, refers to someone/something already known that can be uniquely identified. 
        + *The tree* only works if the tree has been previously mentioned or clear from context
        + *A tree* the tree hasn't been previously mentioned and its identity can't be inferred from context
    - *Demonstratives*: this, that
* *Adjectives*: describe properties of nouns
    - Attributive/adnomial: a red rose, this long journey, many intelligent children, a very trendy magazine
    - Predicative use as a complement of *be*: the rose is red, the journey will be long
    - Positive (rich, trendy), comparative (richer, trendier), superlative (richest, trendiest). Or, alternatively, periphrasic forms, formed with auxiliary word (more, most).


###### Brown tags

* Determiners
    - Articles: AT
    - Singular determiners (this, that): DT
    - Plural determiners (these, those): DTS
    - determiners that can be singular/plural (some, any): DTI
    - double conjunction determiners (either, neither): DTX
    - Quantifiers: words that express ideas like "all, many, some"
        + Pre-quantifiers (all, many): ABN
        + Nominal pronoun (one, something, anything, somebody): PN
    - There (...is a bear in the garden): EX
    - Interrogative pronouns, used for questions and relative clauses
        + WH-determiners (what, which): WDT
        + Objective WH-pronoun (whom, which, that): WPO
        + Nominative WH-pronoun (who, which, that): WPS
* Adjectives
    - Positive form: JJ
    - Comparative form: JJR
    - Superlative form: JJT
    - Semantically superlative (chief, main, top): JJS
    - Cardinals (one, two): CD
    - Ordinals (first, second): OD


### 3.1.3. Verbs

Verbs are used to describe actions, activities and states. Forms:  
* Base form
* Present tense
* Infinitive
* Progressive (action in progress): she is *walking*
* Gerund (derived form where the verb gains some or all the properties of nouns): this is the most vigorous *walking* I've ever done. *Walking* is fun
* Present perfect
* Past perfect

##### Features commonly marked on verbs

| Feature category| Instances |
|---------------- |-----------|
| subject person  | singular, plural |
| subject person  | first, second, third |
| tense           | present, past, future tense |
| aspect          | progressive, perfect |
| mood/modality   | possibility, subjunctive, irrealis |
| participles     | present participle (walking), past participle (walked) |
| voice           | active, passive, middle |

###### Brown tags

* Base form (take): VB
* Third person singular (takes): VBZ
* Past tense (took): VBD
* Gerund and present participle (taking): VBG
* Past participle (taken): VBN
* Modal auxiliaries (can, may, must, could, might): MD

### 3.1.4. Adverbs, prepositions and particles

* *Adverbs* modify a verb in the same way that adjectives modify nouns. They specify place, time, manner or degree. Some adverbs can also modify adjectives (a very unlikely event)
    - Degree adverbs/qualifiers: very
* *Prepositions* are small words that prototypically express spatial relationships: in, on, over, about, concerning
* *Particles* are subclass of prepositions that can enter into strong bonds with verbs in the formation of so called *phrasal verbs* (take off, give in, take on, put off)

###### Brown tags

* Ordinary adverb (simply, late): RB
* Comparative adverb (later, better, less): RBR
* Superlative adverb (latest, best, least): RBT
* Qualifier (very, too, extremely): QL
* Post-qualifier (enough, indeed): QLP
* Prepositions: IN
* Particles: RP


### 3.1.5. Conjunctions and complementizers

Coordinating conjunctions conjoin/coordinate two words or phrases of (usually) the same category  

* husband *and* wife (nouns)
* she bought *or* leased the car (verbs)
* the green triangle *and* the blue square (noun phrases)
* she bought her car, *but* she also considered leasing it (sentences)

Coordinating conjunctions link 2 sentences/clauses like in the examples. This can be done by subordinating conjunctions

* she said *that* she would be late (proposition)
* she complained *because* he was late (reason)
* I won't wait *if* he is late (condition)
* she thanked him *although* he was late (concession)
* she left *before* he arrived (temporal)

Cases of subordinating conjunctions like *that* or use of *for* that introduce arguments of the verb are alternatively called **complementizers**. 

Coordination is joining two sentences as equals. Subordination is attaching a secondary sentence, usually expressing a proposition/reason/condition/concession/temporally related event, to a primary sentence

###### Brown tags

* Conjunctions: CC
* Subordinating conjunctions: CS




## 3.2. Phrase structure

Words are organized into phrases, groupings of words that are clumped as a unit, and they follow a word order. Syntax is the stud of the regularities and constraints of word order and phrase structure. Certain groupings of words behave as *constituents*, which can be detected by their being able to occur in various positions, and showing uniform syntactic possibilities for expansion.

* I put the *bagels* in the freezer
* The *bagels*, I put in the freezer
* I put in the freezer the *bagels* (that John gave me)


* *Noun phrases (NP)*: a noun is usually embedded in a noun phrase, a syntactic unit of the sentence in which information about the noun is gathered. The noun is the head of the noun phrase, the central constituent that determines the syntactic character of the phrase. Noun phrases are usually the arguments of verbs, the participants in the action/activity/state described by the verb
* *Prepositional phrases (PP)*: headed by a preposition and contain a noun phrase complement. Common in NP and VP where they express spatial/temporal locations and other attributes
* *Verb phrases (VP)*: the verb is the head of the verb phrase. The VP organizes all elements of the sentence that depend syntactically on the verb
    - *Getting to school on time* was a struggle
    - He *was trying to keep his temper*
    - That woman *quickly showed me the way to hide*
* *Adjective phrases (AP)*: less common
    - She is *very sure of herself*
    - He seemed a man who was *quite certain to succeed*


### 3.2.1. Phrase structure grammars

A syntactic analysis of a sentence tells who does what to whom in the event described in a sentence: 

* Mary gave Peter a book
* Peter gave Mary a book

In free word order languages (Latin, Russian), there are various ways of ordering words without the meaning changing, and case marking is used to indicate who did what to whom. In English, the basic word order is Subject - Verb - Object (basic sentences are declarative sentences). In general, the order is modified only to express particular mood categories, or interrogatives, imperatives. Rules can be written such as:

* S: NP VP
    - NP:
        + AT NNS
        + NP PP
        + ...
    - VP:
        + VP PP
        + VBD
        + ...
    - P: IN NP
    - ...

With these rules, sentences can be derived:

* S
* NP VP
* AT NNS VBD
* The children slept

and

* S
* NP VP
* AT NNS VBD NP
* AT NNS VBD AT NN
* The children ate the cake

The more intuitive way of representing phrase structure is as a tree. The leaf nodes are terminal nodes and the internal nodes nonterminal nodes. A local tree is a nonterminal node and its immediate daughters. Each node in the tree shows something we are hypothesising to be a constituent.


### 3.2.2. Dependency: arguments and adjacents

"Sue watched the man at the next table". Sue and the man are dependents of a watching event, they're two arguments of the verb watch. The PP *at the next table* is a dependent of *man*, since it modifies it. Noun phrases (NP) are arguments of verbs. The arguments can be classified by:

* semantic roles
    - agent: person/thing doing something
    - patient: person/thing having something done to it
    - instrument
    - goal
* One can describe the syntactic possibilities for arguments in terms of grammatical relations
    - subject: noun phrase before the verb
    - object: noun phrase, normally immediately after the verb
    - pronouns: in the subject case when they are subjects of a verb, and in the object case when they are objects of a verb
    - indirect object: recipient in the dative case

Verbs can be:

* Transitive verbs have a (direct) object
    - she brought a bottle of whiskey
* Intransitive verbs don't have an object
    - she walked (along the river)

Other components:

* Arguments: the subject, object and direct objects are arguments. Arguments express entities that are centrally involved in the activity of the verb. Arguments are divided into the subject, and all non-subject arguments (complements). Most arguments are expressed as NPs, but can be expressed as PPs, VPs or as clauses:
    - we deprived him *of food*
    - john knows *that he is losing*
* Adjuncts: are phrases that have a less tight link to the verb. Adjuncts are always optional while many complements are obligatory. Adjuncts also move around more easily than complements. Adjuncts tell the time/place/manner of the action/state that the verb describes
    - she saw a Woody Allen movie *yesterday in Paris*
    - she saw a Woody Allen movie *with great interest*
* Subordinate clauses (sentences within a sentence) can also be either adjuncts or subcategorized arguments.



## 3.3. Semantics and pragmatics

The study of meaning of individual words (or lexical semantics) and the study of how meanings of individual words are combined into the meaning of sentences. How are words related to each other? Words can be organized into a lexical hierarchy, such as WordNet:

* Hypernym/hyperonym: a word with more general sense than the other. animal is hypernym of cat
* Hyponym: word with a more specialized meaning. cat is hyponym of animal
* Antonym: word with opposite meanings
* meronym: part-whole relationship. tire is meronym of car, leaf is meronym of tree
* holonym: opposite of meronym
* synonyms: words with very similar meaning. car, automobile
* homonym: words written the same way, but two different words with different meanings.
* homophone: two words are written the same way and have identical pronunciation

Other concepts:

* compositionality: the meaning of the whole cannot be strictly predicted from the meaning of the parts
    - white paper, white hair, white skin, white wine. It's a different kind of white every time
* collocations: the meaning of the whole is the sum of the meanings of the part + some additional semantic component that can't be predicted from the parts
* idiom: the relationship between the meaning of the words and the meaning of the phrase is completely opaque
    - kick the bucket = die
* scope: the scope extends over one or more phrases or clauses
    - everyone didn't go to the movie


## 3.4. Conclusion
Linguistics is divided into:

* Phonetics: study of the physical sounds, consonants, vowels, intonation
* Phonology: structure of sound systems
* Morphology
* Syntax
* Semantics
* Pragmatics: study of how knowledge about the world and language conventions interact with literal meaning. 
    - hurricanes are disasters