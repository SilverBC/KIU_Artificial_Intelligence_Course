## This week covers Knowledge Based Inferences and Machine Logic 
1) Terminology in Knowledge problems, 
    * Sentence
    * Propositional Logic 
    * Knowledge Base
    * Model 
    * Clause
    * Disjunction/Conjuction 
    * Universal/Existential Quantification
2) Propositional Logic is constructed with Propositional Symbols and Logical Connectives
    * Propositional Symbols: Letters(P,Q,R....)
    * Logical Connectives:  NOT(), AND(), OR(), Implication(), Biconditional()
3) Model Checking 
<br>methodically explores and verifies all possibilities to check whether a given proposition is true, given our knowledge base. 

4) Inference Rules

| Inference Rule | Mathematical Expression | Description |
|----------------|-------------------------|-------------|
| Modus Ponens   | $$ \begin{array}{c} \alpha \rightarrow \beta \\ \alpha \\ \hline \beta \end{array} $$ | If "A implies B" is true and A is true, then B must also be true. |
| And Elimination           | $$ \begin{array}{c} \alpha \land \beta \\ \hline \alpha \end{array} $$ | If an 'And' proposition is true, any one element of it is true. |
| Double Negation Elimination | $$ \begin{array}{c} \neg(\neg\alpha) \\ \hline \alpha \end{array} $$ | A double negation cancels out, making the statement true. |
| Implication Elimination   | $$ \begin{array}{c} \alpha \rightarrow \beta \\ \hline \neg \alpha \lor \beta \end{array} $$ | An implication can be rephrased as 'not A or B'. |
| Biconditional Elimination | $$ \begin{array}{c} \alpha \leftrightarrow \beta \\ \hline (\alpha \rightarrow \beta) \land (\beta \rightarrow \alpha) \end{array} $$ | A biconditional splits into two implications. |
| De Morgan’s Law           | $$ \begin{array}{c} \neg(\alpha \land \beta) \\ \hline \neg \alpha \lor \neg \beta \end{array} $$ | The negation of 'And' is 'Or' with negated components. |
|                           | $$ \begin{array}{c} \neg(\alpha \lor \beta) \\ \hline \neg \alpha \land \neg \beta \end{array} $$ | The negation of 'Or' is 'And' with negated components. |
| Distributive Property     | $$ \begin{array}{c} \alpha \land (\beta \lor \gamma) \\ \hline (\alpha \land \beta) \lor (\alpha \land \gamma) \end{array} $$ | 'And' distributes over 'Or'. |
|                           | $$ \begin{array}{c} \alpha \lor (\beta \land \gamma) \\ \hline (\alpha \lor \beta) \land (\alpha \lor \gamma) \end{array} $$ | 'Or' distributes over 'And'. |
| Resolution     | $$ \begin{array}{c} P \lor Q \\ \neg P \\ \hline Q \end{array} $$ | If one of two propositions in an Or proposition is false, the other must be true. |
|                | $$ \begin{array}{c} P \lor Q \\ \neg P \lor R \\ \hline Q \lor R \end{array} $$ | Resolution can be applied to deduce a new Or proposition when one part of the initial Or proposition is negated. |

5) The Final idea is to transform the KnowledgeBase into it's CNF (Conjuctive Normal Form) for easier inferences. 
<br>&nbsp;&nbsp;&nbsp;&nbsp; In order to check if Knowledgebase Entails some 'A' we need to see if it is produces an empty clause. if empty clause occurs with KB ⊨ ~A

6) First Order Logic
<br> Uses 2 types of symbols for succint knowledge expression as opposed to Propositional Logic which may get too verbose. 
    * Constant Symbols
    <br>&nbsp;&nbsp;&nbsp;&nbsp; Represent Objects: ex, Human, Dog, Company
    * Predicate Symbols 
    <br>&nbsp;&nbsp;&nbsp;&nbsp; Represent Relations/Functions: ex, BelongsTo(Human, Company)
