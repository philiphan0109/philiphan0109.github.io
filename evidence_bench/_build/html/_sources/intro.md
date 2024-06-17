# Evidence Bench

[![EvidenceBench Paper](https://img.shields.io/badge/Paper-blue.svg?logo=read-the-docs&logoColor=white)](https://link_to_your_paper) [![LEI Lab](https://img.shields.io/badge/Lab%20Group-LEI%20Lab-blue.svg?logo=teams&logoColor=white)](https://lei.ucsd.edu/) [![GitHub](https://img.shields.io/badge/GitHub-EvidenceBench-blue.svg?logo=github&logoColor=white)](https://github.com/EvidenceBench/EvidenceBench)

## Introduction

Welcome to **EvidenceBench**! Our goal is to provide a robust benchmark for evaluating language models on their ability to retrieve evidence supporting or refuting scientific hypotheses from biomedical papers. Our pipeline involves high-quality, sentence-by-sentence annotations, validated by human experts, across over 400 papers and 700k sentence judgments. This work supports the development of automated tools for evidence synthesis and hypothesis testing in the biomedical domain.


![Figure 1](_figs/fig1.png)

<p style="text-align: center; font-size: smaller; line-height: 1.2;">Figure 1: In EvidenceBench, a model sees a hypothesis, and the full sequence of sentences from a paper as a candidate pool. The goal is to select sentences that provide evidence for or against the hypothesis. The retrieved sentences are compared to ground-truth study aspects, collected from literature surveys, which identify relevant evidence from the paper. In this case, the model selects S9, S69, and S106 as the set of retrieved sentences. However, these 3 sentences only cover study aspects 1, 3, and 4. Aspect 3 is missed, resulting in 75% Aspect Recall.</p>

## An Example

Imagine a scenario where researchers are trying to determine whether a chemical found in traditional Chinese herbal medicines, Aristolochic Acid (AA), causes kidney cancer. Twenty years ago, this causal relationship was still under investigation. The evidence for this relationship is now spread across a vast research literature.

EvidenceBench presents the task of extracting evidence for or against a hypothesis from a specific paper. In this example, the task is to identify evidence from the paper [Hoang et al. (2016)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5533284/).

The **Survey Summary** provides a ground-truth description of the relevant evidence. It is extracted from a survey article on Aristolochic Acid, and gives a concise overview of key findings from Hoang et al. (2016). The **Hypothesis** is the central question the researchers are trying to answer, in this case, whether AA-induced DNA mutations cause kidney cancer.

**Survey Summary**: Results from Hoang et al. (2016) showed that a cumulative ingestion of more than 250 mg of AA increased the risk of ccRCC with an odds ratio (OR) of 1.25. A distinctive AA mutational signature was evident in 6/10 sequenced ccRCC exomes from AA-exposed patients. Among these tumors, VHL, the most frequently mutated gene, mutated in 7 out of 10 samples.

**Hypothesis**: Aristolochic Acid (AA) induced DNA mutation is causal for renal carcinoma (RCC).

EvidenceBench breaks the Survey Summary into Study Aspects, and then compares these aspects to each sentence in Hoang et al. (2016), generating per-sentence annotations for the paper. 

**Study Aspects** (generated from Survey Summary):

1. **Increased Risk of ccRCC**: The study found that consuming more than 250 mg of AA increases the risk of ccRCC, with an odds ratio (OR) of 1.25. 
    - "Cumulative ingestion of more than 250 mg of AA increased risk of ccRCC (OR, 1.25), and we detected dA-AL-I adducts in 76% of Taiwanese ccRCC patients." (Sentence 9)
    - "The results (Table 1) indicate an adjusted OR of 1.25 (1.004–1.547) for ccRCC in persons consuming more than 250 mg of AA during the period of 1997 to 2003." (Sentence 69)

2. **AA Mutational Signature**: A unique mutation pattern caused by AA was found in 6 out of 10 ccRCC patients.
    - "Whole-exome sequencing confirmed that the AA mutational signature was present in 6 of 10 ccRCC patients studied." (Sentence 163)

3. **Frequent Mutation of VHL Gene**: The gene VHL was the most frequently mutated in these cancer cases.
    - "VHL was the most frequently mutated driver gene (7/10 tumors) in our AA-exposed ccRCCs (Table 2)." (Sentence 106)

4. **VHL Mutation Prevalence**: VHL was mutated in 7 out of 10 tumors in the study.
    - "VHL was the most frequently mutated driver gene (7/10 tumors) in our AA-exposed ccRCCs (Table 2)." (Sentence 106)

**Selected Sentences from Full Paper**: The following sentences from Hoang et al. (2016) are sources of information for the Survey Summary. These sentences are annotated with their corresponding Study Aspects. The EvidenceBench task is to retrieve these sentences given the paper's full-text.

- Sentence 9: Cumulative ingestion of more than 250 mg of AA increased risk of ccRCC (OR, 1.25), and we detected dA-AL-I adducts in 76% of Taiwanese ccRCC patients. *Study Aspect 1*

- Sentence 69: The results (Table 1) indicate an adjusted OR of 1.25 (1.004–1.547) for ccRCC in persons consuming more than 250 mg of AA during the period of 1997 to 2003. *Study Aspect 1*

- Sentence 106: VHL was the most frequently mutated driver gene (7/10 tumors) in our AA-exposed ccRCCs (Table 2). *Study Aspects 3 and 4*

- Sentence 163: Whole-exome sequencing confirmed that the AA mutational signature was present in 6 of 10 ccRCC patients studied. *Study Aspect 2*
