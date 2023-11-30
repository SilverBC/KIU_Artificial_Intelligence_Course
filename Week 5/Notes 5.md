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
| Sigmoid  | $`f(x) = \frac{1}{1 + e^{-x}}`$ | Differentiable, useful in probailities | Vanishing Gradient: gradients can get really small, slowing down training |
| ReLu     | $`f(x) = \begin{cases} x & \text{if } x \geq 0 \\ 0 & \text{otherwise} \end{cases}`$ | Faster, Mitigates Vanishing Gradient | Dying ReLu: some neurons may stop contributing |


