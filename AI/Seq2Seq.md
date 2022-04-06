#### Seq2Seq
Seq2seq stands for the Sequence-To-Sequence architecture. which is also known as the [[encoder-decoder]] architecture. [[Seq2Seq]] is typically implemented based on sequence models such as [[Recurrent Neural Network|RNNs]] or [[Gated RNNs]].
###### Defenition
![[The architecture of seq2seq.png]]
Seq2seq defines the [[probability]] of generating $y$ conditioned on $x$ as $P (y|x)$. Fig. 2.4, a [[seq2seq]] model consists of:
- (1) an input [[Recurrent Neural Network|RNN]] or encoder $f_1$ that encodes input sequence $x$ into context vector $c$, usually as a simple function of its final hidden state; and
- (2) an output [[Recurrent Neural Network|RNN]] or decoder $f_2$ that generates output sequence $y$ conditioned on $c$. $x$ and $y$ can be of different lengths. The two [[Recurrent Neural Network|RNNs]], parameterized by θ, are trained jointly to minimize the loss function over all the pairs of $(x, y)$ in training data.$$L(\theta)=\frac{1}{M}\sum_{i=1...M}log-P_\theta(y_i|x_i)??.$$