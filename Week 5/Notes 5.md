## This week starts delving Deeper into Perceptrons mentioned in the previous lecture, we go deep on foundational theory of Neural Networks. 

<div align="center">
<img src="./images/image-1.png" />
</div>

As shown in the diagram above, we will be discussing 3 points about Neural Networks. Structural Aspects, Training and Optimization, Practical Implementation and Considerations. 

Neural Network: Mathematical Model that learns a function for mapping Inputs and Outputs

### 1) Structural Aspects
* Activation Functions 

| Function | Mathematical Expression | Advantages    | Disadvantages       |
|----------|-------------------------|---------------|---------------------|
| Step     | $`f(x) = \begin{cases} 1 & \text{if } x \geq 0 \\ 0 & \text{otherwise} \end{cases}`$ | Simple, Provides clear binary output | Not Differentiable  |
| Sigmoid  | $`f(x) = \frac{1}{1 + e^{-x}}`$ | Differentiable, useful in probabilities | Vanishing Gradient: gradients can get really small, slowing down training |
| ReLu     | $`f(x) = \begin{cases} x & \text{if } x \geq 0 \\ 0 & \text{otherwise} \end{cases}`$ | Faster, Mitigates Vanishing Gradient | Dying ReLu: some neurons may stop contributing |

* Gradient Descent
<br> Algo used for minimizing loss when training Neural Networks: 
    * Starts with, Random Weights 
    * Repeats until done:
        * Calculate gradient towards decreasing loss based on ALL points given 
        * Updates weights according to the gradient 
    * There are several other variations as calculating gradient based on ALL points given can be costly
        * Stochastic: calculates based on one point 
        * Mini-Batch: calculates based on small group of points

* BackPopagation
<br> Vital part of Gradient Descent algorithm, that calculates error for the output layer and until it reaches the input layer, it keeps propagating the error back one layer. after that it updates the weights accordingly. 

### 2) Structural Aspects: 
* Multi-Layer Neural Networks 
<br>In order to gain capability of separating non-linear data we need to add hidden layers. Those hidden layers can be combined from one layer to another and by combining their outputs, Neural Networks can create non-linear borders.

* Convolutional Neural Networks 
<br> In case of data structures that would take a lot of neural networks in order to fully understand such as images. which can reach over a million pixels, representing each pixel with an input neuron is unfeasible. This is why before inputting such information into Neural Networks, we go through layers of Convolution and Pooling.

    * Convolution layer: Kernels such as "edge detection" kernel are used to learn patterns from the images

    * Pooling layer: after learning patterns images no longer need to be massive in resolution, they can be pooled to reduce image size

    * Several of the above mentioned images, can be chained depending on the specific case. 

* Reccurent Neural Networks 
<br> Reccurent Neural Networks are neccessary for tasks where the neural network needs to consider present states on top the previous output. Similar concept is used in Electrical Engineering with Feedback circuits. 

### 3) Practical implementations and Considerations 
* overfitting 
    * this is an everlasting problem with Neural-Networks. in order to mitigate it, neurons can be randomly dropped out, in order to make sure that the function is not over-reliant on some neurons. 
* Computer Vision 
    * This is an ML problem for analyzing and understanding images.
        * Image convolution, ie, applying kernels as filters in order to find out patterns is common practice
* TensorFlow 
    
    SOME CODE EXAMPLES WILL BE ADDED LATER. 


