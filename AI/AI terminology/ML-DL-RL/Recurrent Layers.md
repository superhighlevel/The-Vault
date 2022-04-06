#### Recurrent Layers
An example of [[Recurrent Neural Network]]  is shown here:
![[Recurrent neural networks.png]] [[Recurrent Neural Network|RNNs]] are commonly used for [[sentence embedding]] where we view a text as a *sequence of words* rather than a [[Bag-Of-Words|BOW]]. They map the text to a dense and low-dimensional semantic vector by *sequentially* and *recurrently* processing each word, and mapping the subsequence up to the current word into a low-dimensional vector as $h_i = RNN(x_i , h_{i−1}) := g(W_{ih}^\intercal x_i + W_r^\intercal h_{i−1})$, where:
	$x_i$ is the word embedding of the $i$-th word in the text, 
	$W_{ih}$ and $W_r$ are trainable matrices, and 
	$h_i$ is the [[Semantic Sepresentation|semantic sepresentation]] of the word sequence up to the $i$-th word