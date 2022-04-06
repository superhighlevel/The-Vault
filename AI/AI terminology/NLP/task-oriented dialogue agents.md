[[Task-Oriented Dialog]] [[Agents]]
![[Pasted image 20220329163108.png]]
&nbsp;&nbsp;&nbsp;&nbsp;A typical [[task-oriented dialogue agents]] is composed of four modules:
1. [[NLU]] module for identifying user [[intents]] and extracting associated information.
2. A [[state tracker]] for tracking the dialogue state that captures all essential  
information in the conversation so far.
3. A [[dialogue policy]] that selects the next action based on the current state.
4. A [[NLG]] module for converting agent actions to natural language responses. 

&nbsp;&nbsp;&nbsp;&nbsp;In recent years there has been a trend towards developing [[fully datadriven systems]] by unifying these modules using a [[DNN|deep neural network]] that maps the user input to the agent output directly.