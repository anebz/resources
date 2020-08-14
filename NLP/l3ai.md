# L3AI conference 2020

## [Effective conversation design](https://www.youtube.com/watch?v=TCRRvDRln0U) - Vittorio Banfi

### Examples of conversation design patterns

**Dedicated repair path**, what to do when the bot and user don't understand each other. A way to repair the conversation back to the original conversation path. Like in a pizza ordering service, if the delivery address isn't found. Get the user into giving a correct address.

**Multi-level repair path**, what happens if you can't repair during the repair path. Design the repair path of the repair path. Give it 3 tries to get the address correctly. If it fails, offer the user to talk to a human.

**Slot filling path**, when you need multiple data points from the user in order to complete an intent. The user should be able to express these things in an unordered way. The bot can ask 2 question, the user can give in the answers both in the same message, first one and then the second, or vice versa. And the bot should manage this. In this case, the engagement time depends on the user. How much time they want to spend interacting with the bot.

## [Robust NLU for voice assistants](https://www.youtube.com/watch?v=DYgANb2wCuM) - Karthik Raghunathan

Automatic speech recognition (ASR) has many errors when dealing with uncommon names, domain-specific terms. Most ASRs work as black boxes and don't give much room for customization. But we can assume that given an audio input, the black box returns a list of hypothesis transcripts and the confidence for each.

ASR:

1. Feature extraction
2. Acoustic model (AM)
3. Language model (LM)

In the NLP pipeline, there are many steps:

1. Domain classifier
2. Intent classifier
3. Entity recognizer
4. Role classifier
5. Entity resolver
6. Language parser

Ways to make the NLU more resilient to ASR errors

### ASR n-best rescoring

Use in-domain knowlege to bias the ASR output. We can't change the LM inside ASR, but we can create our own LM. Take training data from the output of ASR, and build own in-domain LM. With this, we can rescore and rerank the hypotheses. The in-domain LM takes into account the real-world usages of the hypotheses, rather than frequency in the audio data. This approach doesn't create any new hypotheses, just reranks them.

### Training with noisy data

Add common ASR errors to your NLU training data. If the sentence 'join the meeting' is often mislabeled as 'shark the meeting', we can add the shark message to the training data. We only add examples of missed transcribed queries that are fairly common.

### ASR-robust entity resolution

Entity resolution is the task of noting a detected entity in the user input to a canonical concrete entity in your knowledge base. If the input is 'call Sheryl', we can link 'Sheryl' to the entity in our knowledge base, which is {'name': 'Sheryl', 'employee_id': 123} for example. This problem can be modeled as an information retrieval problem, you can create the knowledge base in elastic search. If we see entity resolution as a 'search' problem, we can have 2 approaches:

* Fuzzy matching
    - normalized tokens (Oleary -> O'Leary)
    - Character n-grams (Ashley -> Ashlee)
    - Word n-grams (Carly Rae -> Carly Rae Jepsen)
    - Edge n-grams (Monica -> Malica)
* Semantic matching
    - Domain-specific entity synonyms (Sid -> Siddharth, Bob -> Robert)

To make ASR more robust regarding entity resolution, we can introduce phonetic similarity features, and a phonetic space where different phrases with vastly different meanings are close to each other, if they sound similar. The way to map this is doing the double metaphone algorithm, a rule-based algorithm mapping a given word into a phonetic code so that similar words have similar phonetic encoders. A more recent approach is to use a ML [grapheme-to-phoneme (G2P)](https://www.github.com/cmusphinx/g2p-seq2seq) which transforms a given piece of text into a sequence of phonemes. These 2 techniques provide complementary information so we used features from both techniques.

## [From research to production](https://www.youtube.com/watch?v=5_lRfLFjfEs) - Tanja Bunk

### Idea

Ideas can come from the community, customers, literature, or internal sources.

### Research proposal

1. Collect ideas for possible solutions by reading relevant literature, papers, blog posts.
2. Formulate the problem and the possible solutions in a research proposal
3. Discuss the proposal in the team

### First implementation

Goal is to implement a working version so that we can verify if our possible solution works or not. Don't write production-ready code, don't polish code, document, etc. But the code should be readable and adaptable.

### Experiments

Take the code, configure some features and hyperparameters, and get the data. Check the results, and depending on that adapt code/config/data accordingly. Usually this is repeated this a couple of times, and finally decide if you want to continue with the idea or discard it.

A bottleneck might be the data, choosing the right dataset is challenging. Is there something available, can we adapt an existing dataset so that it fits our needs, do we have to create a new dataset? Is that feasible?

Reasons to rule the idea out might be that the accuracy of the model is terrible, or that our solution is very slow. Accept it if the classification results are good, or time is slightly increased.

### Production-ready implementation

Follow the coding guidelines, polish code, add docstrings, tests and documentation.

### Feedback

Share the production-ready version with community members for early feedback, adapt the implementation based on this, before releasing.

### Experimental release

Research features might work in some use cases but not in others, so Rasa releases research features as experimental. They can be modified or removed in the future, feedback is continually collected.

### Remove, adapt or release features

Depending on the feedback, adapt the feature, or remove it completely because it doesn't work for most use cases.

## [Distilling BERT](https://www.youtube.com/watch?v=Xji8NmL3FvQ) - Sam Sucik

BERT is huge, so it's distilled into different student models by transfer learning. The students are divided into BERT and LSTMs. Once students are trained, they're probed, given encodings, given a probing classifier and output scores.

This is knowledge distillation, BERT is reduced insofar the knowledge lost isn't much.

For each NLP task, BERT is distilled differently.

1. Tune important hyperparameters, batch size, learning rate, scheduler, type of embedding (word2vec, WordPiece)
2. Start with 2.4M-parameter students, try different sizes

See how it performs on different NLP tasks. It's possible to distil BERT into 1000x smaller and faster students.

## [Designing practical NLP solutions](https://www.youtube.com/watch?v=JpkzK58lkmA) - Ines Montari

How to make NLP projects not fail so often. We might need an estimate of what the accuracy should be, and the data & workflow will vary depending on this. To test this, we need some labelled data but to label data we need to know how the annotation scheme should look, and what we want to label and predict. Instead of iterating only on the code, we also need to iterate on the data as well.

Sometimes, there is no dataset or model adapted to your specific problem. you need to take the business problem apart and convert it into machine learning problems tha can be solved cost-effectively, efficient and a high chance of success.

How to do this? First, the data might be noisy and if you're looking for company sales not all data might be about it. So train a **text classifier** to get only company sales. Then run an **entity recognizer** to find the buyer, seller and sell price. Then you could train an entity linker to match the alias company names, e.g. Github, to Github. Inc., a real entity. Finally you can use a currency normalizer to adapt the price to your desired currency.

If your business problem is specific, provide a small number of specific examples and combine different NLP techniques.
