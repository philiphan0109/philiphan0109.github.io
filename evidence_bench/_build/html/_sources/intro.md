# Evidence Bench

[![EvidenceBench Paper](https://img.shields.io/badge/Paper-NeurIPS-blue.svg?logo=read-the-docs&logoColor=white)](https://link_to_your_paper) [![LEI Lab](https://img.shields.io/badge/Lab%20Group-LEI%20Lab-blue.svg?logo=teams&logoColor=white)](https://lei.ucsd.edu/) [![GitHub](https://img.shields.io/badge/GitHub-EvidenceBench-blue.svg?logo=github&logoColor=white)](https://github.com/EvidenceBench/EvidenceBench)

## Task Formulation

We created a pipeline for high-quality, sentence-by-sentence annotation of biomedical papers to find evidence for hypotheses. The pipeline, validated by human annotators, is used to evaluate various language models and retrieval systems on a benchmark of over 400 papers and 700k sentence judgments. Despite improvements, the best models still fall short of expert-level performance. This work aims to support the development of tools for automated evidence synthesis and hypothesis testing.

The ***EvidenceBench*** benchmark aims at identifying the most important pieces of information for or against a hypothesis within a paper. This sentence retrieval task is to retrieve the sentences which provide this evidence.

### Definitions

``Candidate Pool`` The full paper is presented as a list of sentences. This list of sentences is the Candidate Pool. 

``Study Aspect`` A study aspect is a single piece of information described in a paper. This could be an experimental outcome or a detail from study design.

``Source of Information`` A sentence is a paper is considered a source of information for a study aspect if it satisfies the following two criteria:

1. The content of the sentence implies most of the study aspect.
2. For any part of the study aspect that the sentence does not imply, the information must be deducible from the surrounding context.

``Hypothesis`` A hypothesis is a scientific generalization, expressible in one sentence. It should not be specific to one experiement. 

``Evidence Set`` The evidence set is the set of study aspects which provides evidence for or against a hypothesis. We use papers and the sentences in them to curate the evidence set.

### Evidence Retrieval @ K

Our primary task is Evidence Retrieval @ K (``ER @ K``) - to find the k sentences from the candidate pool (paper) which provide evidence for or against the hypothesis. The retrieved sentences are then evaluated against the evidence set, which contains the ground-truth study aspects that provide evidence for or against the hypothesis.

The goal is for the retrieved sentences to be sources of information for study aspects in the evidence set. The system does not have access to the evidence set, it is only for evaluation.

The second version of a task is that only study aspects delated to the results and analyses are considered. Those related to background and methodolody are omitted from the evidence set. This is ``Result-ER @ K`` and it provides a more targeted evaluation of the system's ability to identify the most important evidence.

### An Example

Aristolochic Acid (AA) is a toxin that is naturally occurring in traditional Chinese herbal medicines and has been known to cause many types of cancer in animals and humans. However, 20 years ago, the causal relationship between AA and kidney cancer was not yet confirmed. In this section, we present an example data instance related to AA.

**Hypothesis**: Aristolochic Acid (AA) induced DNA mutation is causal for renal carcinoma (RCC).

**IARC-Style Summary**: Results from Hoang et al. (2016)[15] showed that a cumulative ingestion of more than 250 mg of AA increased the risk of ccRCC with an odds ratio (OR) of 1.25. A distinctive AA mutational signature was evident in 6/10 sequenced ccRCC exomes from AA-exposed patients. Among these tumors, VHL, the most frequently mutated gene, mutated in 7 out of 10 samples.

**Study Aspect Decomposition**:

1. Cumulative ingestion of more than 250 mg of AA increased the risk of ccRCC (OR, 1.25). [Sentences 9 and 69 are sources of information for Aspect 1].
2. A distinctive AA mutational signature was evident in six of the 10 sequenced ccRCC exomes from AA-exposed patients. [Sentence 163 is the source of information for Aspect 2]
3. The most frequently mutated driver gene was VHL. [Sentence 106 is the source of informa- tion for Aspect 3].
4. VHL was mutated in 7 out of 10 tumors. [Sentence 106 is the source of information for Aspect 4]

**Study Aspect Decomposition**:

All 216 sentences from Hoang et al. are indexed, starting from 0 to 215. For brevity, we will not reproduce the entire paper here. Figure 1 shows sentences 9, 69, 106 from the full list of sentences are retrieved by a model.

**Selected Sentences from Full Paper**:

- Sentence 9: Cumulative ingestion of more than 250 mg of AA increased risk of ccRCC (OR, 1.25), and we detected dA-AL-I adducts in 76% of Taiwanese ccRCC patients.

- Sentence 69: The results (Table 1) indicate an adjusted OR of 1.25 (1.004–1.547) for ccRCC in persons consuming more than 250 mg of AA during the period of 1997 to 2003.

- Sentence 106: VHL was the most frequently mutated driver gene (7/10 tumors) in our AA-exposed ccRCCs (Table 2).

- Sentence 163: Whole-exome sequencing confirmed that the AA mutational signature was present in 6 of 10 ccRCC patients studied.
