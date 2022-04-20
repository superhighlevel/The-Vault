## A survey of joint intent detection and slot-filling models in natural language understanding
[[Intent classification]] and[[ slot filling]] are two critical tasks for [[Natural Language Understanding]]. Traditionally the two tasks have been deemed to proceed  
*independently*. However, more recently, joint models for intent classification  
and slot filling have achieved *[[state-of-the-art]]* performance, exists a *strong relationship* between the two tasks. This article is  a compilation of past work in joint intent classification and slot filling. 3 milestones: 
- Intent detection to identify the speaker’s intention, 
- slot filling to label each word token in the speech/text,
- joint intent classification and slot filling tasks
In this article, we describe *trends*, *approaches*, *issues*, *data sets*, *evaluation metrics* in [[Intent classification]] and [[slot filling]].
### I. Introduction 
The concept of a *hierarchical semantic frame* has developed to represent the *levels of meaning* within spoken utterances. At the highest level is a [[domain]], then [[intent]] and then [[slots]]. ![[Pasted image 20220419102737.png]]The [[NLU]] task is thus the extraction of the semantic frame elements from the utterance.
In many data sets, and indeed real world applications, *the domain is limited*. In these cases the *domain level* is generally *not part the analysis*. Some dataset like [[SNIPS]] dataset expected to field requests from various domains, inclusion of the domain detection in the problem can lead to better results. However, for the purposes of this survey we will treat the domain as *ancillary*.
This leaves us with [[intent]] and [[slots]] identification.What does the human user want from the communication, and what semantic entities carry the details? The two sub-tasks are known as [[Intent classification|intent detection]] and[[ slot filling]]. The latter may be a *misnomer* as the task is more correctly [[slot labelling]], or [[slot tagging]]. 
It was quickly noted that the slot labels present and the intent class should and do *influence each othe*r in ways that solving the two tasks simultaneously should *garner better results* for both tasks.
![[joint model#A joint model]] 
The most regularly used data sets are two freely available sets [[ATIS]] and [[SNIPS]]. A common experiment is implied by the literature, from which the reported results are compared in this survey. In addition, one of the aims of this survey is to address further *standardisation*, in terms of the *parameters* of the experiment and the *evaluation metrics used*.
In summary, this survey address three major questions:
1. How do these joint models achieve and balance two aspects, [[intent classification]] and [[slot filling]]?
2. Have *syntactic clues/features* been fully exploited or does semantics override this consideration?
3. Can successful models in one supervised domain be made more generalisable to new domains or languages or unseen data?
#### Scope
Focus on extraction of the intent and slots of single utterances. Papers on the following aspects will be reviewed but the information considered as ancillary only:
- Multi-domain data sets with annotated domain.
- Dialogue action.
- Multi-intent data sets.
- Automatic speech recognition (ASR).
### OVERVIEW OF THE LITERATURE
#### Introduction 
| Year | papers | Feature engineering                                                                            | Technologies                                                                                                                            | 
| ---- | ------ | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | 
| 2011 | 1      | Neural network, observation feature vector                                                     | Deep learning, CRF                                                                                                                      | 
| 2012 | 1      | n-gram, K-DCN                                                                                  | Kernel learning, deep learning, DCN, log-linear model                                                                                   |  
| 2013 | 3      | Discriminative embedding, named entity,  dependency parse, POS, SENNA, RNNLM,  bag-of-words    | DBN, RNN, RNN-LM                                                                                                                        | 
| 2014 | 2      | RNN, lexicon feature                                                                           | CRF, LSTM, regression model, deep learning                                                                                              |  
| 2015 | 3      | Word embedding, named entity, word em-  bedding                                                | RNN, sampling approach, external memory                                                                                                 |
| 2016 | 3      | Word embedding, context window, RNN,  CNN                                                      | BiRNN, attention, LSTM, encoder-labeler, CNN                                                                                            |
| 2017 | 1      | Word embedding                                                                                 | (Bi)LSTM, encoder-decoder, focus mechanism, entity position-aware  attention                                                            |   
| 2018 | 5      | BiLSTM, word embedding, character, CNN, delexicalisation                                       | CRF, MTL, segment tagging, NER, BiLSTM, attention, delexicalised sentence generation, DNN, reinforcement learning, GRU, pointer network |  
| 2019 | 6      | Word embedding, web-data, expert feedback, contextual information, GloVe, POS, character, BERT | BiLSTM, BiGRU, different knowledge sources, context gate, MTL, CNN                                                                      |
| 2020 | 2      | ResTDNN                                                                                        | Prior knowledge driven label embedding, CRF, TDNN, RNN                                                                                  |
![[Intent classification]]

#### Major Areas of Research
Research into intent classification in [[SLU]] has generally come from four areas: [[search engines]], [[question answering systems]], [[dialogue systems]], and [[text categorisation]]. Moreover, [[intent classification]] can be applied in more general [[NLP]] tasks, such as[[ text classification]], [[sentiment analysis]] and [[scientific citation]].
#### Overview of technological approaches
Before 2015, most papers focused on classical [[ML|machine learning]] approaches, such as [[SVM]], [[K-nearest neighbours]] and [[random forest]]. Features used by these models were mainly generated by [[dependency parsing]], [[word embedding]] and[[n-grams]]. One [[Deep Learning|deep learning]] method explored early on was [[deep belief networks]] (DBN). In more recent years, with the success of[[ deep learning]] in other areas, [[NN|Neural Network]], especially [[Recurrent Neural Network|RNNs]], started to be widely used for this task. [[Attention]] mechanisms have been integrated in models for identifying which parts of sentences should contribute to the classification. 
#### Issues addressed in intent detection
In this section we survey the issues encountered in the literature around intent detection, and the solutions proposed.The issues may be specific to the task, like ambiguity of semantic intent. They may be general machine learning issues like lack of training data, and dealing with new or adapting domains. They may be issues specific to the available data like imbalanced data, short sentences, or the  
[[out-of-vocabulary]] (OOV) issue.
##### Ambiguity in interpretation
In essence, this issue is at the heart of[[ intent classification]]; identifying the decision boundary between samples *close together* in feature space, yet belonging to *different classes*. This issue may be more prevalent with *short texts*, since they may include *insufficient information* and not follow correct grammar.
Early approach propose a rich feature representation. A more recent approach proposed training on a [[triple dataset]] - an anchor sample, a positive sample in the  
same class and a negative sample from a different class. *Combining [[convolutional]] and [[BERT]] [[Encoding (NLP)]] of each one and mapping them to Euclidean space with Siamese shared weights*, an intermediate loss of the anchor-positive distance minus the anchor-negative distance is minimised
##### Lack of labelled training data or small training sets

### JOIN INTENT AND SLOT MODELS
The joint task marries the objectives of the two sub-tasks. Research in the joint task has largely come from the personal assistant or chatbot fields. The chatbot is usually task-oriented within a single domain, while the personal assistant may be single or multi-domain.
#### Overview of technological approaches
##### Classical methods
The earliest work on the joint task used a tri-level [[CRF]] with the three layers being [[tokens|token]] features, slot labels and intent labels. showed this architecture performed better than performing the two sub-tasks in a pipeline. Other early statistical models used a maximum entropy model ([[MEM]]) for intent and a [[CRF]] for slot labelling, and a multilayer  [[Hidden Markov model]]. 
##### Recursive neural networks
[[RecNN]]   
The earliest attempt at a neural model to address the joint task was use a [[RecNN|Recursive neural networks]]. A combined loss over the slots and intent (and domain) is [[backpropagation|backpropagation]]. An optional post-processing, [[Viterbi decoded Markov layer]] is applied to the slots.
##### Recurrent neural networks
In 2016 the power of the [[Recurrent Neural Network|RNN]] circuit for [[seq2seq]] tasks was explored in multiple papers. Features representing [[tokens]] are passed in temporal sequence to [[Recurrent Neural Network|RNN]] units  
which have a hidden state. Intermediate hidden states may be used for slot labelling. The final hidden state is an embedding of the entire utterance and may be used for intent prediction. The classic [[encoder-decoder]], which produces a sequential output, is the most commonly used architecture. Issues with the original  
[[Recurrent Neural Network|RNN]] cells are addressed by [[Long-Short Term Memory|LSTM.]] and [[Gated Recurrent Unit|GRU]] cells. [[Bidirectional RNN]], where the input sequence is passed in in both forward and backward direction, address issues with unidirectional capturing of context.
##### Attention
[[Attention]] is an obvious technique for forcing an interaction between information from the two sub-tasks, in a learned way. 
In early papers a basic concept of attention used was the weighted sum of [[Bi-RNN]] hidden states as an input to slot and intent prediction. The base circuit is a [[BiLSTM]] taking word vectors in sequence and using a different learned weighted sum of the intermediate states of the [[BiLSTM]] for each slot prediction (the slot  
attention) and the final state for intent detection. The new addition is a slot gate which takes the current slot attention vector and combines it with the current intent vector in an attention operation. The output of the slot gate feeds the slot prediction. This circuit is an early example of [[intent2slot]], a path through the circuit where intent prediction information is also fed explicitly to the slot prediction  
element
[[Transformer]]. The transformer architecture a non-recurrent model useful for capturing global dependencies via [[multi-head self-attention]]. Model attention is applied between all these to inform the intent prediction sub-task where it gives a superior result.
##### Hierarchical models
A hierarchical model passes information learned to be relevant through ordered levels. While this flow is explicit it is often unidirectional.
##### Bi-directional models
A model where there is a pipeline from one sub-task to the other may be seen as unidirectional. A bi-directional model, different to the bi-directionality seen in RNNs, has an explicit path from slot processing into intent prediction and also from intent processing into slot prediction. This can form two parallel paths through the circuit, often with a fusion layer or a joint loss.
##### Memory networks
The network begins with [[GloVe]] word embeddings and [[max pooled]] [[convolutional character embeddings]]. These feed the first memory block, which constructs slot features, intent features and hidden states. Further memory blocks in the stack take the previous block’s hidden states as inputs. The memory blocks perform three  
operations, which also strive to capture local context and global sequential patterns: 
- Deliberate Attention: a *slot memory* (with number of cells equal to number of slot labels) and *intent memory* (ditto for number of intent labels) are *randomly initialised* then updated. At each word position each memory is updated as a *weighted sum of the other memory* and of the block hidden states for the current word. Diffusion of influence between slots and intents thus takes place and can inform the hidden states for the next word. 
- Local Calculation: this is a recurrent process receiving the input embeddings or previous block’s hidden states. It calculates *slot representation* and *intent representations* as interactions between its inputs and the slot and intent memories. It is an *[[Long-Short Term Memory|LSTM.]] network*.
- Global Recurrence: a [[BiLSTM]] layer on top which encodes global sequential interactions.
After the stacked blocks a final prediction takes place. Slots are labelled via a [[CRF]] on the final hidden states and slot representations. Intent is via an average of the final hidden states and intent representations.
##### Graph networks
The META of NLP world
[[Graph networks]] can be used to address shortcomings of limited context windows suffered by RNNs and  CRFs, as they can learn global relationships between words and labels.


