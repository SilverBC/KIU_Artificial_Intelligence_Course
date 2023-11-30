## This week starts delving into more modern machine learning techniques, namely Supervised, Unsupervised and Reinforcement learning techniques and their uses. 

In essence, the task is to create some mathematical function that can map inputs to outputs.

Supervised Learning mainly works with labeled data and is used for classification and regression tasks, while Unsupervised Learning works with unlabeled data and clusters data based on patterns it discovers. Reinforcement Learning on the other hand through Trial and Error uses Markov Decision Process to find a strategy that maximizes some reward(s).

Additionally, we may use Support Vector Machines (SVM)-s, to bring in additional dimensions to our problems to better classify, this way non-linear and discontinuous data can get accurate borders. An example of an SVM is below: 
* Maximum margin separator: 
<br>gives instruction to the algorithm to create a boundary in such a way that it keeps most distance between $n$ groups within the training set. 


1) Supervised Learning
* Classification
    <br>Some example Approaches are: 

    * Nearest-Neighbor Classification: Assiginging variable in question the value of the closest known observation(s) 
    * Perceptron Learning: 
    draws a line boundary, data is classified based on which side it ends up on 
    <br>The perceptron hypothesis 
    In this implementation, both hard and soft thresholds may be used, hard thresholds tells us Yes/No while soft thresholds additionally tell us confidence %. we will go deeper on activation functions in the next lecture. 
    
    <br>function, denoted as **h(x)**, is a simple binary classifier that can be used for linear classification tasks. It takes an input vector **x** and produces an output of 1 or 0 based on a threshold:

$$
h(x) = \begin{cases} 
1 & \text{if } \sum_{i=0}^{n} w_i x_i \geq 0 \\
0 & \text{otherwise} 
\end{cases}
$$

with each new data, the weights get adjusted accordingly: 

$$ w_i = w_i + \alpha (y - h_w(x)) x_i $$


* Regression 
<br> Unlike classification tasks where inputs are mapped to discrete values, regression maps inputs to some continous values. 

2) Unsupervised learning: 
    * Clustering: 
<br> without any labels, groups data by some patterns discovered within the training set. 

3) Reinforcement Learning 
Uses markov decision process to map out some $ actions(s) $ in a statespace based on final rewards. The ultimate goal being finding a strategy for choosing actions that maximize reward. One of the ways this can be achieved is through Q learning algorithm.
when action taken: 
* Estimates $ Q(s, a) $ based on current and expected rewards 
* Updated $ Q(s, a) $ taking in account both old and new estimations
<br> $ Q(s,a) = Q(s,a) + α(new value estimate - Q(s,a)) $ 
or
<br> $ Q(s,a) = Q(s,a) + α((r - γmax_αQ(s',a')) - Q(s,a)) $ 
where α = weight of new esimate
      γ = weight of new reward estimate

In reinforcement learning, Exploration vs Exploitation, Both are often necessary but proportions are case specific. 
* Greedy Decision-Making: always exploits, never explores. 
* Random Exploration: always explores, never exploits. 
* Epsilon-Greedy Exploration: with a certain probability $  ε $ , the agent selects a random action, and with probability $ (1 - ε) $, it chooses the best-known action based on Q-values.


4) Optimizations: 
    * Loss Functions:  Quantifying utility loss, larger loss = less accuracy
    <br> $ L(\text{actual}, \text{predicted}) = | \text{actual} - \text{predicted} | $
    <br> Square Loss: $ L(\text{actual}, \text{predicted}) = (\text{actual} - \text{predicted})^2
 $  <- penalizes outlies more harshly 

    * OverFitting:  if training data is too specific and the model is overtrained, issues with generalizations rise up, this is why we apply Regularization. 
        * Regularization: penalizes more complex hypothesises to avoid overfitting. 
        <br>$ cost(h) = loss(h) + γComplexity(h) $
        <br>where,  γ = how harshly complexity is penalized. 






