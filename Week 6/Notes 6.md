## This week starts dealing with Natural Language Processing, more specifically topics such as context free grammar and Tranformer models. 

<div align="center">
<img src="./images/image.png" />
</div>


Syntax and Semantics: 
* Syntax: Sentence Structure in Gramatical Sense
* Semantics: Meaning of words 
Text Processing Techniques: 

### 1) Syntax and Semantics 
#### 1) Context-Free Grammar
Abstracting sentence meaning in favor of representing it as it's formal Grammar Structure, for sentence "She saw the city" would be for example:

```ascii
      S
     / \
    ↙︎   ↘︎
   NP    VP
   ↓     ↙︎ ↘︎
   N    V    NP
   |    |    ↙︎ ↘︎
   |    |    D   N
   ↓    ↓    ↓    ↓ 
  she  saw  the  city
```





