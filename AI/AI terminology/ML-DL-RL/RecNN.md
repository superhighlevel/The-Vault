---
aliases: Recursive neural networks
---
!! Different to [[Recurrent Neural Network]] 
#NLP, #AI
#### Recursive neural networks
RecNNs work over trees, in  [[Natural Language Understanding|NLU]] the constituency parse tree of the utterance, with leaves corresponding to the words (represented by word vectors). A [[NN|Neural Network]] applied at each node of the tree, recursively upwards to the root, computing a state for each node. At each node the states from children nodes are combined with a weight vector representing the node’s syntactic type. Individual slot label classifiers are applied  
to each leaf using a combination of the word vectors of itself and its neighbours and the state vectors along the path from the leaf to the root. The state at the root is passed to an intent classifier.