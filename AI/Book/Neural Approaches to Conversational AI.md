# Neural Approaches to Conversational AI
[[QA]], [[Task-Oriented Dialog]] and [[Social Chatbots]]

### Chapter 1. Introduction
[[Conversational AI]] is fundamental to natural user interfaces. Attracting [[NLP]], [[IR]]
and [[ML]] communities. [[SIGIR 2018]] has created a new track of [[AI]], [[Semantics]], and [[intelligent dialogue system]] to bridge research in [[AI]] and [[IR]], especially targeting [[QA]], deep semantics and dialogue with [[intelligent agents]].
- Overral survey of neural approaches to [[Conversational AI]], targeting [[NLP]] and [[IR]] audiences, not including [[SLU]]:
	- We provide a comprehensive survey of the neural approaches to [[Conversational AI]] that have been developed in the last few years, covering [[QA]], [[Task-Oriented Dialog]] and [[Social Chatbots]] with a unified view of optimal decision making.
	- We draw ==connections== between ==modern neural approaches== and ==traditional approaches==, allowing us to better understand why and how the research has evolved and to shed light on how we can move forward.
	- We present [[state-of-the-art]] approaches to training dialogue agents using both [[Supervised Learning]] and [[RL]].
	- We sketch out the landscape of [[conversational systems]] developed in the research community and released in industry, demonstrating via case studies the progress that has been made and the challenges that we are still facing.

#### 1.1 Who Should Read this Paper?
The [[IR]] and [[NLP]] communities as the primary target audience. 
* This survey is structured as follows:  
	• The rest of this chapter introduces [[dialogue tasks]] and presents a unified view in which [[open-domain dialogue]] is formulated as an optimal decision making process.  
	• **Chapter 2** - Introduces basic [[mathematical]] tools and [[ML]] concepts, and reviews recent progress in the [[Deep Learning]] and [[RL]] techniques that are fundamental to developing [[intelligent agents]].  
	• **Chapter 3** - Describes [[QA agents]], focusing on neural models for [[knowledge-base QA]] and [[MRC]].  
	• **Chapter 4** - Describes [[task-oriented dialogue agents]], focusing on applying [[deep reinforcement learning]] to [[dialogue management]].  
	• **Chapter 5** - Describes [[Social Chatbots]], focusing on fully data-driven neural approaches to  end-to-end generation of conversational responses. 
	• **Chapter 6** - Gives a brief review of several [[conversational systems]] in industry.  
	• **Chapter 7** - Concludes the paper with a discussion of [[research trends]].
#### 1.2 Dialogue: What Kinds of Problems?
- The example illustrates the kinds of problems a [[intelligent dialogue system]] is expected to solve: 
	- [[QA]]: the agent needs to provide concise, direct answers to user queries based on rich knowledge drawn from various data sources including text collections such as Web documents and pre-compiled knowledge bases such as sales and marketing datasets.
	- [[task completion]]: the [[Agents]] needs to accomplish user tasks ranging from restaurant reservation to meeting scheduling and to business trip planning. 
	• [[social chat]]: The [[Agents]] needs to converse seamlessly and appropriately with users — like a human as in the Turing test — and provide useful recommendations. 

A typical [[task-oriented dialogue agents]] is composed of four modules...
Most [[Task-Oriented Dialog]] are implemented using a [[modular system]], where the bot often has access to an external database on which to inquire about information to accomplish the task. 
[[Social Chatbots]], on the other hand, are often implemented using a [[unitary system]].  
#### 1.3 A Unified View: Dialogue as Optimal Decision Making.
[[Decision making process]] ... Basically, it divides tasks into hierarchies and solves it from low to high.  
If we view each option as an action, both top- and low-level processes can be naturally captured by the [[RL intelligent dialogs system]].   
* Amazon Alexa Prize, and Microsoft XiaoIce use a hierarchical dialogue manager: 
	* A master (top-level) that manages the overall conversation process, 
	* A collection of skills (low-level) that handle different types of conversation segments (subtasks).

Because [[RL intelligent dialogs system]] is expensive to train, therefore, in practice, we often use a hybrid approach that combines the strengths of different ML methods.
![[Pasted image 20220330153935.png]]

#### 1.4 The Transition of NLP to Neural Approaches
Neural approaches are now transforming the field of [[NLP]] and [[IR]], where symbolic approaches have been dominating for decades.
NLP applications differ from other data processing systems in their use of language knowledge of various levels, including [[phonology]], [[morphology]], [[syntax]], [[Semantics]] and [[discourse]]. Historically, much of the [[NLP]] field has organized itself around the architecture of Fig. 1.3, with researchers aligning their work with one component task, such as [[morphological analysis]] or [[parsing]]. These tasks can be viewed as resolving (or realizing) [[natural language ambiguity]] (or diversity) at different levels by [[mapping]] (or [[generating]]) a natural language sentence to (or from) a series of human-defined, unambiguous, [[symbolic representations]], such as Part-Of-Speech ([[POS]]) tags, context free grammar, first-order predicate calculus.
Neural approaches do not rely on any human-defined [[symbolic representations]] but learn in a task-specific neural space where task-specific knowledge is implicitly represented as semantic concepts using low-dimensional continuous vectors.
![[Pasted image 20220330154336.png]]
Fig. 1.4 illustrates, ![[neural methods in NLP tasks#Neural methods in NLP tasks]]
### Chapter 2. Machine Learning Background
This chapter presents a brief review of the [[Deep Learning|Deep Learning]] and [[RL|Reinforcement Learning]] technologies that are most relevant to [[Conversational AI]] in later chapters.
#### 2.1. Machine Learning Basics 
Mitchell (1997) defines [[ML|Machine Learning]] broadly...
- Dialogue, as summarized in [[Table 1.1]], is a well-defined learning problem with T, P, and E specified as follows:
	• T: perform conversations with a user to fulfill the user’s goal.  
	• P: cumulative reward defined in [[Table 1.1]].  
	• E: a set of dialogues, each of which is a sequence of user-agent interactions.

As a simple example, a single-turn QA dialogue agent might improve its performance as *measured by [[Accuracy]] or relevance of its generated answers at the [[QA]] task*, through experiences of *human labeled question-answer pairs*.

* A common recipe of building an ![[ML Agents using supervised learning#ML Agents using Supervised Learning]]
* ![[Common Supervised Learning Metrics]]
* ![[RL|Reinforcement Learning]]
A central challenge in both [[Supervised Learning|SL]] and [[RL]] is *generalization*, the ability to perform well on unseen inputs. Many learning theories and algorithms have been proposed to address the challenge with some success by, e.g., seeking a good tradeoff between the amount of available training data and the model capacity to avoid [[underfitting]] and [[overfitting]]. Compared to previous techniques, neural approaches provide a potentially more effective solution by leveraging the representation learning power of [[DNN|deep neural network]], as we will review in the next section.  
#### 2.2. Deep Learning
![[Deep Learning#Deep Learning]]
##### 2.2.1 Foundations
Consider a [[text classification problem]]: labeling a text string (e.g., a document or a query) by a domain name such as “sport” and “politics”. 
	![[Figure 2.1#Flowcharts of classic machine learning Left and deep learning Right A convolutional neural network is used as an example for deep learning]]
For [[NLP]] tasks, depending on the type of linguistic structures that we hope to capture in the text, we may apply different types of [[Neural Network Layer]] structures, such as [[convolutional layers]] for local word dependencies and [[Recurrent Layers]] for global *word sequences*. These layers can be combined and stacked to form a *deep architecture* to capture different semantic and context information at different abstract levels. Several widely used [[Neural Network Layer|Neural Network layer]] are described below:
	![[Word Embedding Layers#Word Embedding Layers]]
	![[Fully Connected Layers#Fully Connected layers]] [[Convolutional-Pooling Layer]]
	![[Recurrent Layers]]

##### 2.2.2. Two Examples
This section gives a brief description of two examples of [[DNN]] models, designed for the [[ranking]] and [[Text Generation|text generation tasks]], respectively. They are composed of the [[Neural Network Layer|NN layers]] described in the last section.
**[[DSSM]] for [[ranking|Ranking]]**. In a ranking task, given an input query $x$, we want to rank all its candidate answers $y ∈ Y$, based on a similarity scoring function [[Cos similarity|sim]]$(x, y)$. The task is fundamental to many [[IR]] and [[NLP]] applications, such as [[query-document ranking]], [[answer selection]] in [[QA]], and [[dialogue response selection]]. ![[DSSM#DSSM]]
![[Seq2Seq for Text Generation#Seq2Seq for Text Generation]]
#### 2.3. Reinforcement Learning
![[RL#Foundations]]
![[RL#Foundations]]