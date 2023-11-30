## This week covers Knowledge Based Inferences and Machine Logic 
### 1) Terminology in Knowledge problems, 
* Sentence
* Propositional Logic 
* Knowledge Base
* Model 
* Inference
* Clause
* Disjunction/Conjuction 
* Universal/Existential Quantification
### 2) Propositional Logic is constructed with Propositional Symbols and Logical Connectives
* Propositional Symbols: Letters(P,Q,R....)
* Logical Connectives:  NOT(), AND(), OR(), Implication(), Biconditional()
### 3) Model Checking 
<br> methodically explores and verifies all possibilities to check whether a given proposition is true, given our knowledge base. 

### 4) Inference Rules

| Inference Rule                | Mathematical Expression | Description |
|-------------------------------|-------------------------|-------------|
| Modus Ponens                  | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`  \begin{array}{c} \alpha \rightarrow \beta \\ \alpha \\ \hline \beta \end{array} `$ | If "A implies B" is true and A is true, then B must also be true. |
| And Elimination               | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \alpha \land \beta \\ \hline \alpha \end{array} `$ | If an 'And' proposition is true, any one element of it is true. |
| Double Negation Elimination   | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \neg(\neg\alpha) \\ \hline \alpha \end{array} `$ | A double negation cancels out, making the statement true. |
| Implication Elimination       | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \alpha \rightarrow \beta \\ \hline \neg \alpha \lor \beta \end{array}`$ | An implication can be rephrased as 'not A or B'. |
| Biconditional Elimination     | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \alpha \leftrightarrow \beta \\ \hline (\alpha \rightarrow \beta) \land (\beta \rightarrow \alpha) \end{array} `$ | A biconditional splits into two implications. |
| De Morgan’s Law               | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \neg(\alpha \land \beta) \\ \hline \neg \alpha \lor \neg \beta \end{array} `$ | The negation of 'And' is 'Or' with negated components. |
|                               | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \neg(\alpha \lor \beta) \\ \hline \neg \alpha \land \neg \beta \end{array} `$ | The negation of 'Or' is 'And' with negated components. |
| Distributive Property         | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \alpha \land (\beta \lor \gamma) \\ \hline (\alpha \land \beta) \lor (\alpha \land \gamma) \end{array} `$ | 'And' distributes over 'Or'. |
|                               | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} \alpha \lor (\beta \land \gamma) \\ \hline (\alpha \lor \beta) \land (\alpha \lor \gamma) \end{array} `$ | 'Or' distributes over 'And'. |
| Resolution                    | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} P \lor Q \\ \neg P \\ \hline Q \end{array} `$ | If one of two propositions in an Or proposition is false, the other must be true. |
|                               | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $`\begin{array}{c} P \lor Q \\ \neg P \lor R \\ \hline Q \lor R \end{array} `$ | Resolution can be applied to deduce a new Or proposition when one part of the initial Or proposition is negated. |




#### The final step involves converting the KnowledgeBase into its Conjunctive Normal Form (CNF) to facilitate simpler inferences.

This step is essential for determining if the KnowledgeBase entails a certain proposition 'A'. To do this, we need to check if the combination of the KnowledgeBase and the negation of 'A' (represented as KB ⊨ ~A) leads to an empty clause. The occurrence of an empty clause indicates that 'A' is indeed entailed by the KnowledgeBase.


### 6) First Order Logic
<br> Uses 2 types of symbols for succint knowledge expression as opposed to Propositional Logic which may get too verbose. 
* Constant Symbols
<br>&nbsp;&nbsp;&nbsp;&nbsp; Represent Objects: ex, Human, Dog, Company
* Predicate Symbols 
<br>&nbsp;&nbsp;&nbsp;&nbsp; Represent Relations/Functions: ex, BelongsTo(Human, Company)
