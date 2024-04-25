##### Before Getting Deep into Math, here are some useful Resources: 

#### Visualizations: 
* Surface level visualization of backpropagation in action: https://www.youtube.com/watch?v=Ilg3gGewQ5U
* Continuation of the video above, going a bit deeper on math: https://www.youtube.com/watch?v=tIeHLnjs5U8

##### Articles: 
* building Neural Networks from 0: https://victorzhou.com/blog/intro-to-neural-networks/



<h3 align="center">Network Training</h3>

- **How to determine the network parameters**?

  Same as for polynomial curve fitting in linear regression: **minimize a sum-of-squares error function**.


- Lets given a training set comprising a set of **input vectors** $\{\mathbf{x}_n\}$, where $n = 1, ..., N$, and **weights vector** $\{\mathbf{w}\}$together with a corresponding set of **target vectors** $t_n$ we **minimize the error function**:

  $$E_{\mathbf{w}} = \frac{1}{2} \sum_{n=1}^{N} || y(\mathbf{x}_n, \mathbf{w}) - t_n||^2.$$
  
  
- Lets assume that $t$ **has a Gaussian distribution**:

  $$p(t | \mathbf{x, w}) = \mathcal{N}(t | y(\mathbf{x,w}), \beta^{-1}),$$

  where $\beta$ is the **precision** (inverse variance) of the **Gaussian noise**.
  
  
- If **input vectors** are **identically distributed observations** $\mathbf{X} = \{\mathbf{x}_1, ..., \mathbf{x}_n\}$, along with corresponding target values $\mathbf{t} = \{t_1, ..., t_n\}$, then:

  $$p(\mathbf{t}| \mathbf{X}, \mathbf{w}, \beta) = \prod_{n=1}^{N} p(t_n | \mathbf{x_n}, \mathbf{w}, \beta).$$
  
  Taking the negative logarithm, we obtain the error function:
  
  $$\frac{\beta}{2} \sum_{n=1}^{N} \{y(\mathbf{x}_n , \mathbf{w}) - t_n\}^2 - \frac{N}{2} \ln \beta + \frac{N}{2} \ln (2\pi),$$
  
  which **can be used** to **learn the parameters** $\mathbf{w}$ and $\beta$.
  

- The value of $\mathbf{w}$ can be found by minimizing the $E(\mathbf{w})$.


- Lets denote the solution by $\mathbf{w}_{\mathrm{ML}}$, because **it corresponds to the maximum likelihood solution**.


- Having found $\mathbf{w}_{\mathrm{ML}}$, the value of $\beta$ **can be found** by **minimizing the negative log likelihood** to give:

  $$\frac{1}{\beta_{\mathrm{ML}}} = \frac{1}{N} \sum_{n=1}^{N} \{ y(\mathbf{x}_n, \mathbf{w}_{\mathrm{ML}}) - t_n\}^2.$$
  

<h3 align="center">Parameter Optimization</h3>

- How to find a **weight vector** $\mathbf{w}$ which **minimizes the chosen function** $E(\mathbf{w})$?

  Because the error $E(\mathbf{w})$ is a smooth continuous function of $\mathbf{w}$ we can we can equate the gradient to zero:
  
  $$\nabla E(\mathbf{w}) = 0$$

- Clearly there is **no hope** of **finding an analytical solution** to this equation.


- Therefore we use **sequential algorithms** such as **gradient decsent method**, or **stochastic gradient descent method**.


- **Note**: there may be (almost allways) **multiple stationary points** and in particular **multiple minima**.

<img src=".\img1.png" width="500" alt="Example" />

<h3 align="center">Error Backpropagation</h3>

- Lets find an **efficient technique** for **evaluating the gradient of an error function $E(\mathbf{w})$** for a **feed-forward neural network**.


- This technique is using a **local message passing scheme** in which **information** is **sent** alternately **forwards** and **backwards** through the network and is known as **error backpropagation**.


- Most **training algorithms** involve an **iterative procedure** for **minimization of an error function**, with adjustments to the weights being made in a **sequence of steps**.
- At **each step**, we can distinguish between **two distinct stages**:
  - In the **first stage**, the **derivatives of the error function** with respect to the weights **must be evaluated**.
  - In the **second stage**, the **derivatives** are **used to compute** the **adjustments** to be made to the **weights**.
  
  
- Many **error functions** of practical interest, for instance those defined by maximum likelihood for a set of **i.i.d. data**, **comprise a sum of terms**, **one for each data point** in the training set, so that:

  $$E(\mathbf{w}) = \sum_{n=1}^{N} E_n(\mathbf{w}).$$
  
  
- Lets consider first a **simple linear model** in which the outputs $y_k$ are linear combinations of the input variables $\mathbf{x}_i$ so that:

  $$y_k = \sum_{n=1}^{N} w_{ki} x_i.$$
  
  An error function takes the form:
  
  $$E_n = \frac{1}{2} \sum_{k} (y_k(\mathbf{x}_n, \mathbf{w}) - t_{nk})^2 = \frac{1}{2} \sum_{k} (y_{nk} - t_{nk})^2.$$
  
- The **gradient of an error function** with respect to a weight $w_{ji}$ is given by:

  $$\frac{\partial E_n}{\partial w_{ji}} = (y_{nj} - t_{nj}) x_{ni}.$$
  
  
- In a **general feed-forward network**, each **unit** computes a weighted sum of its inputs of the form:

  $$a_j = \sum_{i} w_{ji} z_i,$$
  
  where $z_i$ is the **activation of a unit**, that **sends a connection to unit $j$**, and $w_{ji}$ is the **weight associated with that connection**.
  

- Note that $E_n$ **depends on the weight** $w_{ji}$ **only via the summed input** $a_j$ to unit $j$, therefore we can write:

  $$\frac{\partial E_n}{ \partial {w_{ji}}} = \frac{\partial E_n}{\partial a_j} \frac{\partial a_j}{\partial w_{ji}}.$$
  
  Lets introduce a useful notation:
  
  $$\delta_j \equiv \frac{\partial E_n}{\partial a_j}.$$
  
  Using:
  
  $$\frac{\partial a_j}{\partial w_{ji}} = z_i$$
  
  we can finally obtain:
  
  $$\frac{\partial E_n}{\partial w_{ji}} = \delta_j z_i.$$
  
- Thus, **in order to evaluate the derivatives**, we need **only to calculate the value of $\delta_j$** for each **hidden and output** unit in the network.

- For the output units we have:

  $$\delta_k = y_k - t_k$$.

- For the hidden units we have:

  $$\delta_j \equiv \frac{\partial E_n}{\partial a_j} = \sum_{k} \frac{\partial E_n}{\partial a_k} \frac{\partial a_k}{\partial a_j},$$
  
  where the **sum** runs **over all units** $k$ **to which unit $j$ sends connections**.


- Finally, we obtain the following **backpropagation formula**:

  $$\delta_j = h'(a_j) \sum_{k} w_{kj}\delta_k$$
  
  which tells us that the **value of $\delta$** for a particular hidden unit **can be obtained by propagating the $\delta$'s backwards** from units higher up in the network.
  
  <h3 align="center">The Backpropagation Procedure</h3>

<img src="https://drive.google.com/uc?export=view&id=1oumEFeVyZWYPxr1FU5mAMzJ32OF4SrC1" width="300" alt="Example" />


The **backpropagation procedure** can be summarized as follows:

- Apply an input vector $x_n$ to the network and forward propagate through the network using:

  $$a_j = \sum_{i} w_{ji} z_i \textrm{ and } z_j = h(a_j)$$
  to find the **activations** of all the **hidden** and **output units**.

- Evaluate the $\delta_k$ for all the **output units** using:

  $$\delta_k = y_k - t_k$$

- Backpropagate the $\delta$'s using:

  $$\delta_j = h'(a_j) \sum_{k} w_{kj}\delta_k$$
  to obtain $\delta_j$ for each **hidden unit** in the network.
  
- Finally, to **evaluate the required derivatives**, use:

  $$\frac{\partial E_n}{\partial w_{ji}} = \delta_j z_i.$$
  

  <h3 align="center">A Simple Example</h3>

- Lets assume that the **hidden units** have **logistic sigmoid activation functions** given by:

  $$h(a) \equiv \mathrm{tahn}(a),$$
  
  where
  
  $$\mathrm{tahn}(a) = \frac{e^{a} - e^{-a}}{e^{a} + e^{-a}}.$$
  
  A useful feature of this function is:

  $$h'(a) = 1 - h(a)^2$$<br>
  
  
- Lets Considering the **standard sum-of-squares error function**:
  
  $$E_n = \frac{1}{2} \sum_{k=1}^{K} (y_k - t_k)^2$$

  where $y_k$ is the **activation of output unit** $k$, and $t_k$ is the corresponding target, for a particular input pattern $\mathbf{x}_n$.

- **For each pattern** in the training set in turn, we:

  - **perform a forward propagation** using:
    $$a_j = \sum_{i=0}^{D} w_{ji}^{(1)}x_i$$,
    $$z_j = \mathrm{tahn}(a_j)$$,
    $$y_k = \sum_{j=0}^{M} w_{kj}^{(2)} z_j$$.

  - **compute the $\delta_k$** for **each output unit** using:
    
    $$\delta_k = y_k - t_k$$<br>
  
  - **backpropagate** these to **obtain $\delta_j$** for the **hidden units** using:
  
    $$\delta_j = (1 - z_j^2) \sum_{k=1}^{K} w_{kj}\delta_k.$$<br>
    
  - **obtain the derivatives** with respect to the **first-layer** and **second-layer**:
  
    $$\frac{\partial E_n}{\partial w_{ji}^{(1)}} = \delta_j x_i,$$
    $$\frac{\partial E_n}{\partial w_{kj}^{(2)}} = \delta_k z_j.$$
  
  

