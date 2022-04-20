## Joint Multiple Intent Detection and Slot Labeling for Goal-Oriented Dialog
### Abstract
Neural network models have recently gained traction for *sentence-level* [[intent classification]] and *token-based slot-label identification*. In many real-world scenarios, users have *multiple intents* in the same utterance, and a token level slot label can belong to *more than one intent.* We investigate an [[attention-based neural network]] model that performs [[multi-label classification]] for identifying *multiple intents* and produces labels for both intents and slot labels at the token-level. We show state of-the-art performance for both intent detection and slot-label identification by comparing against strong, recently proposed models. Our model provides a small but statistically significant improvement of 0.2% on the predominantly single-intent [[ATIS]] public data set, and 55% intent accuracy improvement on an *internal multi-intent dataset*
### I. Introduction
In [[dialogue systems]], the [[natural language understanding]] component (NLU) is responsible for identifying the user’s request and creating a [[semantic frame]] that succinctly summarizes the user’s needs. These semantic frames are typically constructed using [[intent|intents]] and [[slots|slot-labels]]. The example below shows a user’s request, “*How is the weather in Dallas ?*”. We need to identify the intent (“GetWeatherInfo”) as well as the values for the slot-labels (SL), here, “City” (value=“Dallas”). It is *crucial* that intents and slot-labels are identified with *high accuracy* as an error made by the [[Natural Language Understanding|NLU]] component propagates through downstream components such as the dialog state tracker, the dialog policy and the[[NLG|natural language generation]] components, leading to a substantial *degradation* *performance*.

![[Pasted image 20220420132945.png]]
[[Intent classification|intent detection]] has been modeled as a [[sentence classification]] task where an intent ($y^I$) is assigned to the user’s utterance. Slot labeling is typically modeled as a [[sequential labeling problem]], where a user’s sentence, $x_1,x_2,...x_N$, is labeled with $y_1^S,y_2^S,...y_N^S$, and $y_i^S$ is the slot label assigned to the token at position $i(x_i)$. In the example above, the sequence of slot labels would be, “*O O O O O  City O*”, where, “$O$” stands for “*Other*”.

In real-world scenarios, users indicate *multiple intents* in the same [[utterance]]. For example, a user’s utterance such as, “*show me flights from Dallas to New York and the cost*”, clearly has *two intents*, one for obtaining the price of the flights (“*GetFlightCost*”) and another for the *flight information*. It is *critical* to understand and model such scenarios to allow more *natural interaction* with users. In this paper, we treat the intent detection task as a [[multi-label classification]] problem and suggest various neural network models to obtain multiple intents.

![[Pasted image 20220420134320.png]]

Consider the example in with two intents in the same domain, “BookCab” and “BookHotel”. Suppose “BookCab” has three possible slot labels, “City”, “Time” and pick up location (“Loc”), and suppose that “BookHotel” has slot labels “City”, “CheckinDate”, and “Duration”.
- Consider a user’s utterance, “*book a cab from the airport in Seattle and find me a hotel to stay*”. Here, the user wants to book a cab (“BookCab” intent) as well book a hotel (“BookHotel”). The slot label “Seattle’’ should be assigned to both intents to accurately capture the user’s request. Hence, we study a model that predicts multiple intents both at the token level as well as at the sentence-level

We model token-level multi-intent classification using [[Long-Short Term Memory|Long Short Term Memory]] (LSTMs) units to capture dependencies that may exist between intents. For example, a user who wants to book a cab is also likely to make a request for a hotel in the same utterance but probably not order food i.e., intents such as “BookCab” and “BookHotel” are more likely to occur together when compared to “BookCab” and “OrderFood”. To summarize, the contributions of this paper are:
-  Investigate approaches to the problem of [[multi-intent classification]]. We perform joint multi-intent classification both sentence level and at token-level. We see that,
	- the *token-level multi-intents* help assign user *constraints* to the intents,
	- *sentence-level multi-intent* classification captures *dependencies* between intents.

### Proposed approaches
![[Pasted image 20220420135352.png]]

[[Long-Short Term Memory|LSTM.]]-based [[Recurrent Neural Network|RNN]] models have become popular for [[sequential labeling]], especially in [[NLP|Natural Language Processing]] tasks, due to their ability to model *long-term dependencies*. 
We use a [[BiLSTM]] [[encoder]] to [[Encoding (NLP)]] the input word sequence. The encoder hidden state, $h^{enc}_i$ , at each word position is a *concatenation* of the *forward state* ($fh_i$) and *backward state* ($bh_i$), $$h^{enc}_i = [fh_i; bh_i]$$
