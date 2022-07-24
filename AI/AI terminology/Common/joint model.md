##### A joint model
Which simultaneously addresses each sub-task must, to be successful, capture the *joint distributions* of [[intent]] and [[slot labels]], with respect also to the words in the [[utterance]], their *local context*, and the *global context* in the sentence. A joint model has the advantage over [[pipeline models]] that it is *less susceptible to error propagation*, and over separate models in general that there is a *only a single model* to train and fine tune.
A drawback is that a large annotated corpus is usually required, though this is also true of separate models. The model may also be *relatively complicated* and *take time to train*. It has also been observed that joint models may *not generalise well to unseen data*, due to the variety of natural language expressions of similar intent. In real world applications the domains and label sets may change over time.