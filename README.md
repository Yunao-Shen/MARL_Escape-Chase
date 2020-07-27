# Imitation Learning and Reinforcement Learning in Escape & Chase Games

Rutgers University Computer Graphic Course Project: Imitation Learning and Reinforcement Learning in Escape & Chase Games. 

This project combines with GAIL and curriculum learning to train escapee and chaser agents, in a back and forth approach. Both agents learn to play the game from the demos collected from human player.

## Environment:

The environment include a rectangular playground, a escapee agent in blue, a chaser agent in red and a yellow win zone for escapee.

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/environment.png)

The yellow mask on both agents indicate its facing direction. The red triangle indicates chaser's field of view.

The playground is a randomly generated maze which at least has one path to the win zone. The playground would be different for each episode.

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/generateGround.gif)

We are using first person perspective for the human players while recording demo. We also carefully match the observations of agents with player perspective. So the agents would get most information human player could get, but without getting additional information that huam player can't get.

Espcaee's perspective:

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/escapee_stealth.png)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/escapee_detected.png)

Chaser's perspective

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/chaser.png)

## Training Approach:
This project use generative adversarial imitation learning (GAIL) as core method. From the concept of curriculum learning we constructed a back and forth training approach. The training approach is devided to several sections in which we only train one agent at the same time. But each section the agent is facing better opponent (better trained model) or hard settings (faster opponent's speed or slower own speed) compared to previous section. For each section the GAIL significantly boost the training process. To get more details and data about the whole approach, please see the presentation file: https://drive.google.com/file/d/1LNll3ngYwq-lMZzEGmbOmpSO0l3axeXo/view?usp=sharing

## Final result: the ability and strategy the escapee and chaser agents learn.

### Both agents are able to solve complicate environments such as S-shape path and dead end.

Escapee solves the S-path and dead end:

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/Spath_escapee.gif)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/Dend_escapee.gif)

Chaser solves the S-path and dead end:

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/Spath_chaser.gif)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/Dend_chaser.gif)

### The escapee learns to avoid the chaser, even learn to decide when to avoid or not.

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/avoid1.gif)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/whentoavoid.gif)

### The escapee learns to rush to win zone when the chaser can't catch up with it. It also learns to sneaky behind the chaser when it's not turning back.

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/rush.gif)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/sneaky.gif)

### The chaser learns to investigate where it saw the escapee. Further learn to remember the moving direction of the escapee

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/investigate.gif)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/investigate2.gif)

### The chaser learns to intercept the routine of the escapee, instead of just following behind. The chaser even learns to analyze the routine and predict the possible location where the escapee would show up again.

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/intercept.gif)

![]( https://github.com/Yunao-Shen/MARL_Escape-Chase/tree/master/EscapeAndChase/Images/intercept2.gif)