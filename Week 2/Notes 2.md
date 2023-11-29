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

3) Joint Probability 

    Single variable tables: 

    | R = rain | ~R = ~rain|    
    |----------|-----------| 
    | 0.1      | 0.9       |
    
    | C = cloud | ~C = ~cloud |    
    |----------|-----------| 
    | 0.4      | 0.6       |

    Joint Table where we see how each event correlates with another event. 

    | C \ R   | R  | ~R |
    |---------|----------|-----------|
    | C   | 0.08     | 0.32      |
    | ~C   | 0.02     | 0.58      |

    note: sum of probabilities need normalization to find correct couccurance 

4) Probability Rules 
    
    | Inference Rule                | Mathematical Expression                     | Description |
    |-------------------------------|---------------------------------------------|-------------|
    | Negation                      | $P(\neg a) = 1 - P(a)$                     | $P(\neg a)$ is calculated as $1 - P(a)$, considering all possible worlds add up to $1$. |
    | Inclusion-Exclusion           | $P(a \lor b) = P(a) + P(b) - P(a \land b)$  | Probabilities of $(a \lor b)$ is calculated by summing $P(a)$ and $P(b)$ and subtracting the overlap $P(a \land b)$. This avoids double-counting the cases where both $a$ and $b$ are true. |
    | Marginalization               | $P(a) = P(a, b) + P(a, \neg b)$             | When considering $a$ and $b$ as disjoint probabilities, $P(a)$ can be obtained by adding $P(a, b)$ and $P(a, \neg b)$. |
    | Conditioning                  | $ P(a) = P(a \mid b)P(b) + P(a \mid \neg b)P(\neg b) $ | The probability of $a$ occurring is computed as the sum of conditional probabilities given $b$ and $\neg b$. |

