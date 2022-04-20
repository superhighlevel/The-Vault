#### Sigmoid
The sigmoid is one of the earliest used [[Activation Functions]] in [[NN|neural networks]] history. It takes any real value and squashes it into the range between $0$ and $1$

##### Sigmoid formular
$$f(x)=\dfrac{1}{1+e^{-x}}$$
![[sigmoid.png]]
the sigmoid function saturates (i.e., produces extreme valued outputs) very quickly and for a majority of the inputs.  This can become a problem because it can lead to the gradients becoming either zero or diverging to an overflowing floating-point value. These phenomena are also known as [[vanishing gradient]] problem and [[exploding gradient]] problem, respectively.