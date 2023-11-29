## This week covers how artificial intelligence deals with uncertainty and probabilities. 

1) Axioms of Probability 
    * 0 < P < 1
    * Sum(P(omega) = 1)
    * Random Variable: some x, that can take some set of values {a, b, c} in probabilistic manner. 
    * Unconditional probability: % chance in absence of any other evidence
    * Conditional probaility: % chance given some evidence b

        $$ P(a \mid b) = \frac{P(a \cap b)}{P(b)} $$
    * Independence: a,b are independent if 
        $$ P(a \cap b) = P(a)P(b) $$

2) Bayes Rule 
<br> Given $ P(a \mid b) $ we can calculate $ P(b \mid a) $

$$
P(b \mid a) = \frac{P(b) P(a \mid b)}{P(a)}
$$

3) Join probability 

    | R = rain | ~R = ~rain|    
    |----------|-----------| 
    | 0.1      | 0.9       |

    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+
    
    | C = cloud | ~C = ~cloud |    
    |----------|-----------| 
    | 0.1      | 0.9       |

    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=

    | C \ R   | R  | ~R |
    |---------|----------|-----------|
    | C   | 0.08     | 0.32      |
    | ~C   | 0.02     | 0.58      |

