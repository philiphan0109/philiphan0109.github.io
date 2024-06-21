# Evaluation Metrics & Task Definition

## Evaluation Metrics

### Aspect Recall @K

Aspect Recall @K measures the fraction of study aspects covered by a set of K retrieved sentences. Let {s1, ..., sk} be the set of retrieved sentences and {f1, ..., fm} be the set of study aspects in the evidence set. Aspect Recall @K is defined as:

$$
\text{Aspect Recall @K} = \frac{1}{m} \sum_{f_j} \mathbf{1} \left( \sum_{s_i} S(s_i, f_j) \geq 1 \right)
$$ 

Aspect Recall @K measures the effectiveness of evidence retrieval systems in covering important aspects of a study.

### Evaluation Strategies for LLMs

We implement several LLM prompting strategies:

- **Chain-of-Thought (CoT):** This is our default evaluation strategy, optimized from our development set.
- **In-Context Learning (ICL):** From the development set, we randomly sample 8 example hypotheses and their corresponding ground-truth set of retrieved sentences.
- **Section-by-Section:** We divide a paper into its natural sections. In the first stage, the LLM retrieves sentences from each section one at a time. In the second stage, all retrieved sentences are presented to the LLM.
- **Instruction-following Embedding Systems:** Recent large-scale embedding models are trained to follow various instructions. On the development set, we design a short instruction for embedding models to find information relevant to the hypothesis. The query is formed by concatenating the hypothesis and instruction, and each sentence is independently embedded. Cosine-similarity is used to calculate the top K sentences.


## Task Definitions

### 1. Evidence Retrieval @Optimal (ER @optimal)
- **Description:** Retrieve the smallest number of sentences needed to cover all study aspects.

### 2. Evidence Retrieval @10 (ER @10)
- **Description:** Retrieve no more than 10 sentences to provide evidence for or against a hypothesis.

### 3. Result Evidence Retrieval @Optimal (Result ER @Optimal)
- **Description:** Retrieve the optimal number of sentences covering study aspects labeled as "Results".

### 4. Result Evidence Retrieval @5 (Result ER @5)
- **Description:** Retrieve no more than 5 sentences related to results.

## Notes

- **Train/Test Split:** The dataset is split into training (96 instances), development (37 instances), and test sets (293 instances).
- **Annotation Process:** Sentences in the papers are annotated to determine which provide evidence for the hypotheses, leveraging both expert judgments and automated tools.