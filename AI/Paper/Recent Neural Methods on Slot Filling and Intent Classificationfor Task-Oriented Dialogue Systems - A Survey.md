## Recent Neural Methods on Slot Filling and Intent Classification for Task-Oriented Dialogue Systems: A Survey
### Abtract
In recent years, fostered by [[deep learning]] technologies and by the high demand for [[conversational AI]], various approaches have been proposed that address the capacity to elicit and understand user’s needs in [[Task-oriented dialogue]] system. We focus on two core tasks, [[slot filling]] (SF) and[[ intent classification]] (IC), and survey how neural based models have rapidly evolved to address  
[[natural language understanding]] in[[ dialogue systems]]. We introduce three neural architectures: independent models, which model [[slot filling|SF]] and [[Intent classification|IC]] separately, [[joint models]], which exploit the mutual benefit of the two tasks simultaneously, and [[transfer learning]] models, that scale the model to new domains. We discuss the current state of the research in SF and IC, and highlight challenges that  
still require attention.
### Introduction.
The ability to understand user’s requests is essential to develop effective task-oriented dialogue systems. In a [[dialogue systems]], information is typically represented through a [[semantic-frame structure]], and extracting such representation involves two tasks: identifying the correct frame (i.e.  
[[intent classification]] (IC)) and filling the correct value for the slots of the frame (i.e. [[slot filling]] (SF)).
In recent years, [[NN|neural networks]] based models have achieved the state of the art for a wide range of natural language processing tasks, including SF and IC. Various neural architectures have been experimented on SF and IC, including [[Recurrent Neural Network|RNN]]-based and [[Attention]]-based approaches, till the more recent [[Transformer]] models. [[Input representation]] have also evolved from [[static word embedding]] to [[contextualized word embeddings]]. Such  
progress allows to better address dialogue phenomena involving SF and IC, including [[context modeling]], handling[[out-of-vocabulary]] words, [[long-distance dependency]] between words, and to better exploit the  
synergy between SF and IC through [[joint models]].
### Slot Filling and Intent Classification
![[Task-oriented dialogue#]]



