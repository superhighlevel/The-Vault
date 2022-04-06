Natural hierarchy:
- A top-level process selects what agent to activate for a particular subtask
- a low-level process, controlled by the selected agent, chooses primitive actions to complete the subtask  

&nbsp;&nbsp;&nbsp;&nbsp;Such hierarchical decision making processes can be cast in the mathematical framework of options over [[ Markov Decision Processes (MDPs)]], where options generalize primitive actions to higher-level actions. In a traditional MDP setting, an agent chooses a primitive action at each time step. With options, the agent can choose a “multi-step” action which for example could be a sequence of primitive actions for completing a subtask.