### Chapter 1. Introduction
#### The Supervised Learning Paradigm
![[Supervised Learning]]

#### One-hot Representation
![[One-hot encoding#One-hot encoding]]
#### TF Representation
![[Term Frequency#Term Frequency]]
![[IDF#IDF]]![[TF-IDF]]
### Chapter 2. A Quick Tour of Traditional NLP
   All NLP methods, be they classic or modern, begin with a text dataset, also called a ![[corpus#Corpus]]
   The raw text is a sequence of characters (bytes), but most times it is useful to group those characters into contiguous units called ![[tokens#Tokens]]
In machine learning parlance, the text along with its metadata is called an  
*instance* or *data point*.
The process of breaking a text down into [[tokens]] is called [[tokenization]]. 
[[Types]] are unique [[tokens]] present in a [[corpus]]. The set of all types in a corpus is its [[vocabulary]] or lexicon.
Words can be distinguished as content words and [[stopwords]]. 
![[Feature Engineering#In NLP]]
#### Unigrams, Bigrams, Trigrams, …, N-grams
![[N-grams#N-grams]]
#### Lemmas and Stems
![[Lemmas#Lemmas]]
![[Stems#Stems]]
#### Categorizing Sentences and Documents
[[Categorizing]] or [[Categorizing|classifying]] documents is probably one of the earliest applications of [[NLP]].
The [[Term Frequency|TF]] and [[TF-IDF]] representations are immediately useful for classifying and  
categorizing longer chunks of text such as documents or sentences. Problems such as assigning topic labels, predicting sentiment of reviews, filtering spam emails, language identification, and email triaging can be framed as [[supervised document classification problems]]. 
#### Categorizing Words: POS Tagging
We can extend the concept of labeling from documents to individual words or [[tokens]].  A common example of categorizing words is [[part-of-speech]] (POS) tagging.
#### Categorizing Spans: Chunking and Named Entity Recognition
Often, we need to label a span of text; that is, a contiguous multitoken boundary. For example, consider the sentence, “*Mary slapped the green witch.*” We might want to identify the *noun phrases* (NP) and *verb phrases* (VP) in it.
This is called *chunking* or *shallow parsing*. Shallow parsing aims to derive higher-order units composed of the grammatical atoms, like *nouns*, *verbs*, *adjectives*, and so on. It is possible to write regular expressions over the [[part-of-speech]] tags to approximate shallow parsing if you do not have data to train models for shallow parsing
#### Structure of Sentences
Whereas shallow parsing identifies phrasal units, the task of identifying the relationship between them is called *parsing*. *Parse trees* indicate how different grammatical units in a sentence are related hierarchically
#### Word Senses and Semantics
Words have meanings, and often more than one. The different meanings of a word are called its *senses*
###    Chapter 3. Foundational Components of  Neural Networks
![[Activation Functions]]