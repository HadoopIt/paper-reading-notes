# paper-reading-notes

Some paper reading notes shared with my lab mates. Might be good to keep an archive here.

## Theoretical Impediments to Machine Learning With Seven Sparks from the Causal Revolution
**Authors:** Judea Pearl  
**URL:** https://arxiv.org/pdf/1801.04016.pdf  
**Tag**: Theory  

**Notes:** Judea Pearl, Turing Award winner, claimed in this paper that current machine learning systems (no matter “how deep it is”) have severe theoretical limits on their power and performance in reasoning about interventions and retrospection. This makes such systems not qualified towards achieving strong AI. He claims that a model of the reality (i.e. world model), similar to the ones used in causal inference tasks, is essential to achieving human level intelligence. He describes three layers of causal hierarchy, from Association to Intervention to Counterfactuals. He claims that there exists a sharp classification of causal information in terms of the kind of questions each layer is capable of answering. For example, he pointed out that current deep learning systems operate in the association layer, which is characterized by conditional probabilities. The layer above it, interventional expressions, cannot be inferred from passive observations alone, regardless of how big the data. He believes that the formal restrictions this hierarchy entails explains why statistical based learning systems are prevented from reasoning and from building strong AI. These restrictions also inform us what other information beyond statistics is needed, and in what format, in order to support those modes of reasoning. Finally he explains the 7 pillars of his causal framework.

**My two cents**: It is always good to learn about the boundary of the research we do from the people who work beyond that dimension. It helps us to understand what is doable and what is not, and more importantly, what is worth doing within the boundary.


## A generative vision model that trains with high data efficiency and breaks text-based CAPTCHAs 
**Authors:** D. George, W. Lehrach, K. Kansky, M. Lázaro-Gredilla, C. Laan, B. Marthi, X. Lou, Z. Meng, Y. Liu, H. Wang, A. Lavin, D. S. Phoenix  
**URL:** http://science.sciencemag.org/content/early/2017/10/26/science.aag2612  
**Tag:** Generative Models

**Notes:** A paper published on Science magazine. They proposed a probabilistic generative model that outperforms deep neural networks on a challenging scene text recognition benchmark (CAPTCHAs) while being 300-fold more data efficient. Such generative models address the point that human learns new concepts by generalizing from only a few examples instead of from thousands of examples as deep NN methods do. This usually requires a model to learn from a top-down approach, rather than in a botton-up manner. It reminds me of another generative model paper from CMU Ruslan on human-level concept learning: http://www.cs.toronto.edu/~rsalakhu/papers/LakeEtAl2015Science.pdf


## Generative Adversarial Imitation Learning 
**Authors:** Jonathan Ho, Stefano Ermon  
**URL:** https://papers.nips.cc/paper/6391-generative-adversarial-imitation-learning  
**Tag:** RL; GAN

Notes: Imitation learning is to learn to behave (i.e. learn a policy) by following an expert’s demonstrations. Usually a reward function has to be learned at the same time from the demonstration (i.e. Inverse Reinforcement Learning, IRL) as reward is considered as the most succinct and robust definition of a task [1]. This learned reward function is then used for learning the policy. IRL is a widely used method for imitation learning. GAN for imitation learning is doing exactly the same thing. The generator works as a policy network (i.e. to generate a sequence of actions), and discriminator works as a reward function (i.e. always to give the expert or true action sequence the highest score). The generator or the policy module is optimized with policy gradient. The discriminator or the reward function is optimized in a supervised manner using, say, cross entropy loss or hinge loss. 

**My two cents**: GANs, Inverse Reinforcement Learning, Imitation Learning, all are very popolar terms but internally very closely related.

[1] Ng, Andrew Y., and Stuart J. Russell. “Algorithms for inverse reinforcement learning.” ICML. 2000. http://ai.stanford.edu/~ang/papers/icml00-irl.pdf

## Learning to Act by Predicting the Future 
**Authors:** Alexey Dosovitskiy, Vladlen Koltun  
**URL:** https://openreview.net/pdf?id=rJLS7qKel  
**Tag:** RL; Control

**Notes:** An interesting paper from ICLR 2017 (oral paper). They proposed a method for policy learning by predicting the future observations, instead of by learning from sparse scalar reward. One appealing aspect of this method is that it generalizes to changing goals. This methods won the VizDoom game competition.

**My two cents**: For policy learning in a sequencial decision process that has many steps, learning only from the final scalar reward may require very large number of simulatins and can be very inefficient. This proposed method is more of a supervised learning method, where the agent can learn from every single step. The intuition is that given (1) current observation (e.g. a frame in a video game), (2) your current measurement value (e.g. your health level, dropping below 0 means you are dead), and (3) your goal (i.e. your desired measurement value after taking an action), predicts an action that will most likely to reach your goal. This is quite a clever idea. While, on the negative side, I don’t think such method can be applied in a broad range of applications. Most of the sequencial decision problems that do not involve a simulator will not likely to provide such meaningful information or feedback after taking each action. This makes me wonder the real impact of this proposed method.


## Zero-Shot Learning - The Good, the Bad and the Ugly
**Authors:** Yongqin Xian, Bernt Schiele, Zeynep Akata  
**URL:** https://arxiv.org/pdf/1703.04394.pdf  
**Tags:** Zero Shot Learning

**My two cents:** Probably the last post on this zero-shot learning (ZSL) series. ZSL has gone through rapid development in computer vision over the past few years. This paper categorizes 11 most well known ZSL method variations and performs parallel experiments on a newly defined benchmark. In addition, the author suggests that ZSL research should focus more on the generalized ZSL (i.e. classify among both existing classes and unseen classes during testing) instead of only on pure ZSL (i.e. classify only on unseen classes during testing), as generalized ZSL is of much higher practical value. The generalized ZSL, in my view, is quite similar to domain adaptation in transfer learning, e.g. speaker adaptation in ASR.