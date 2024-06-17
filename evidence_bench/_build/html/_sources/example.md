# An Example

Imagine a scenario where researchers are trying to determine whether a chemical found in traditional Chinese herbal medicines, Aristolochic Acid (AA), causes kidney cancer. Twenty years ago, this causal relationship was still under investigation. The evidence for this relationship is now spread across a vast research literature.

EvidenceBench presents the task of extracting evidence for or against a hypothesis from a specific paper. In this example, the task is to identify evidence from the paper [Hoang et al. (2016)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5533284/).

## Survey Sumamry & Hypothesis Extraction
The **Survey Summary** provides a ground-truth description of the relevant evidence. It is extracted from a survey article on Aristolochic Acid, and gives a concise overview of key findings from Hoang et al. (2016). The **Hypothesis** is the central question the researchers are trying to answer, in this case, whether AA-induced DNA mutations cause kidney cancer.

**Survey Summary**: Results from Hoang et al. (2016) showed that a cumulative ingestion of more than 250 mg of AA increased the risk of ccRCC with an odds ratio (OR) of 1.25. A distinctive AA mutational signature was evident in 6/10 sequenced ccRCC exomes from AA-exposed patients. Among these tumors, VHL, the most frequently mutated gene, mutated in 7 out of 10 samples.

**Hypothesis**: Aristolochic Acid (AA) induced DNA mutation is causal for renal carcinoma (RCC).

## Study Aspect Decomposition
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

## System Sentence Retrieval

**Selected Sentences from Full Paper**: The following sentences from Hoang et al. (2016) are sources of information for the Survey Summary. These sentences are annotated with their corresponding Study Aspects. The EvidenceBench task is to retrieve these sentences given the paper's full-text.

- Sentence 9: Cumulative ingestion of more than 250 mg of AA increased risk of ccRCC (OR, 1.25), and we detected dA-AL-I adducts in 76% of Taiwanese ccRCC patients.

- Sentence 69: The results (Table 1) indicate an adjusted OR of 1.25 (1.004–1.547) for ccRCC in persons consuming more than 250 mg of AA during the period of 1997 to 2003.

- Sentence 106: VHL was the most frequently mutated driver gene (7/10 tumors) in our AA-exposed ccRCCs (Table 2).

- Sentence 163: Whole-exome sequencing confirmed that the AA mutational signature was present in 6 of 10 ccRCC patients studied.
