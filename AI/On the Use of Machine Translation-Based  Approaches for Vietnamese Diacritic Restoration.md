---
aliases: 1709.07104, s
tag: Research, AI
date: 10-05-2022
author: Thai-Hoang Pham, Xuan-Khoai Pham, Phuong Le-Hong.
---
## On the Use of Machine Translation-Based  Approaches for Vietnamese Diacritic Restoration

### Abstract
Study of two [[machine translation]]-based approaches for Vietnamese diacritic  
restoration problem. [[Phrase-based]] and [[Neural Network Layer|Neural Network]]-based machine translation models. On a large dataset, the phrase-based approach has an [[accuracy]] of **97.32%** while that of the neural-based approach is **96.15%.** While the neural-based method has a slightly lower accuracy, it is about **twice faster** than the phrase-based method in terms of inference speed.
### Introduction
**95% Vietnamese words** contain diacritic marks and 80% of these words are ambiguous when removing diacritic marks from them. Vietnamese diacritic marks appear at all vowel characters and one consonant character. There are two types of diacritic marks for Vietnamese. One type (Type-1) is added to a character to transform this character to another one, and another type (Type-2) is used to change the tone of a word
The idea of paper is treating *nondiacritic texts* and *diacritic texts* as *source* and *target languages* in machine translation formulation.
Apply two methods including phrase-based and neural-based machine translation methods. compares the strengths and weaknesses  of these two approaches for this problem. conduct experiments on a large dataset that consists of about 180,000  
sentence pairs to get reliable results - 97.32% and 96.15% on our dataset respectively
### RELATED WORK
Divided into two main approaches: Use of dictionaries and rule sets; using machine learning methods
#### Dictionaries and rule sets
The performance of this approach is *heavily dependent* on *qualities of precompiled dictionaries and rules, and domains of texts*
[VietPad](http://vietpad.sourceforge.net/) - a Vietnamese Unicode text editor, uses a dictionary that stores  
most Vietnamese words to 1-to-1 map from non-diacritic words to diacritics words. This method is not effective because many words in the dictionary do not appear frequently in real texts. Accuracy: **60% to 85%**
[VietEditor](http://lrc.quangbinhuni.edu.vn:8181/dspace/bitstream/TVDHQB_123456789/264/3/Themdautiengviet.pdf)- toolkit alleviate the weakness of VietPad by building the phrase dictionary and uses it after mapping words to find the most appropriate outputs. Accuracy ~ **75%**
#### Machine learning methods
Apply conditional random field ([[CRF]]), support vector machine ([[SVM]]), and [[N-grams|N-Grams]] language models to restore diacritics for Vietnamese texts. 
[viAccent](https://truyentran.github.io/papers/truyen_pricai08.pdf) toolkit that is a combination of [[N-grams|N-Grams]], structured perception and  
[[CRF]]. [[N-grams]] is used as features for [[CRF]] to label diacritics for input sentences. They achieve an [[accuracy]] of **94.3%** on a **newspaper dataset**.
[Diacritics Restoration in Vietnamese: Letter Based vs. Syllable Based Model](https://www.researchgate.net/publication/221420181_Diacritics_Restoration_in_Vietnamese_Letter_Based_vs_Syllable_Based_Model)
gives an empirical study for Vietnamese diacritic restoration by investigating five strategies: learning from letters, learning from semi-syllables, learning from syllables, learning from words, and learning from bi-grams. They combine AdaBoost and C4.5 algorithms to get better results. Their best accuracy is 94.7% when using letter-based feature set.
...
### METHODOLOGY
We treat the diacritic restoration problem as a machine translation problem and apply phrase-based and neural-based machine translation methods for this task. In particular, nondiacritic and diacritic texts are considered as source and target  
languages respectively, and machine translation models are trained to learn how to restore diacritics.
#### Phrase-Based Machine Translation
haha who care about statistic methods in 2022 :D 
#### Neural-Based Machine Transslation
proposed a sequence-to-sequence model that achieved best results for many bi-lingual translation tasks. The general architecture of this model is the combination of two recurrent neural networks. One network encodes a sequence of words in source language into a fixed-length vector representation, and the other decodes this vector into another sequence of words in target language Both of these two networks are jointly trained to maximize the conditional probability of a target sentence given a source sentence. In particular, the conditional probability $p(e|f)$ is computed as
$$log(e|f)=\sum_{j=1}^{m}log\ p(e_j|e_{<j},s)$$
where $s$ is representation vector produced by encoder module
In decoding stage, the conditional probability of a word given previous words is computed as $$p(e_j|e_{<j},s)=softmax(g(h_j))$$
where **hj** is the hidden state at time step **j** of[[Recurrent Neural Network|recurrent neural network]] that computed by previous hidden state and representation vector $s$, and $g$ is a function that transforms the hidden state to [[vocabulary]]-sized vector
![[Pasted image 20220510153512.png]]
### Experiement
#### Dataset
To evaluate these machine translation approaches for this problem on the large dataset, we first collect 10,000 news articles from the web and then remove non-standard characters and diacritics from the original text to build a parallel corpus  
of about 180,000 sentence pairs