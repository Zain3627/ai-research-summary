# Attention Is All You Need

**Authors:** Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, and Łukasz Kaiser 
**Year:** 2017
**Arxiv / Link:** https://arxiv.org/abs/1706.03762
**Area:** LLMs

---

## Problem
There are some two deficiencies in recurrent neural networks the authors wanted to mitigate. 
- The first deficiency is that many computations are sequential which makes it harder to parallelize the training process. 
- The second deficiency is that the number of operations required to relate signals from two arbitrary positions grows linearly for many model and logarithmically for optimized models. This makes learning dependencies between distant words hard.   

---

## Contributions
- The authors proposed a novel deep learning model architecture.
- They achieved state of the art translation performance with a model with training time much faster than neural and recurrence models.

---

## Proposed Solution

### Architecture
This paper introduces new network architecture called transformers. A novel network architecture for sequence transduction tasks that relies entirely on something called *attention*. The architecture in summary follows an encoder-decoder architecture in which there is a process called multi head self attention that happens at the encoder and decoder. ![image](transformers_architecture.png)
### Multi Head Self Attention
Multi head self attention is a process in which each token (word) generates a query (what information I am searching for in other tokens), key (what information I contain), and value (the actual relevant information to be passed). ![image](multi_head_attention.png)
### Positional Encodings
Transformers remove recurrence and convolution so it needs something to sense the relative positions of tokens. The authors generated positional encoded embeddings and added them to the embeddings of each token to interpret the position of the token with its embeddings. 
One important feature in the proposed solution is that 

---

## Experimental Results
That transformer was tested on two translations tasks and was compared with the finest trained models at these tasks. It was obvious that the transformer out performs all models in the BLEU score. One strong point in the transformer also is the huge decrease in its training cost compared to other deep learning architectures. ![image](results.png)

---

## Strengths
This new model has a lot of strong points:
- It has much lower training costs.
- Each token has separate computation which makes a lot of operations parallelized causing a significant drop in the training time.
- The model out scored all previous models in translation tasks becoming the state of the art model at that time.

---

## Weaknesses / Limitations
- The paper focuses mainly on machine translation tasks. Generalization to other sequence modeling tasks can't to be proven still.
- Computational complexity for very long sequence can be exhaustive because of the O(n^2 . d) complexity this architecture has. They tried to propose a solution with more restricted model but its performance wasn't investigated.
- Attention alone has no interpretation for positional information so a positional encoding is necessary. They tried learnable positional encodings and functional positional encodings. Learnable positional encodings showed better performance but this can be done because the learnable parameters increased and it has nothing to do with the positional information. The model should be tested on a dataset built to evaluate the interpretation of the data according to the positional information. 

---

## Reproducibility
This paper results is highly reproducible. Model architecture, training parameters and datasets are clearly explained and versioned.




