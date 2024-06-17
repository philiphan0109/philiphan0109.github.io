# An Example

## Introduction
Imagine a scenario where researchers are investigating the link between Aristolochic Acid (AA), a compound found in traditional Chinese herbal medicines, and kidney cancer. This relationship, questioned two decades ago, now has its proof scattered across extensive research literature.

## EvidenceBench Task Overview
EvidenceBench facilitates the extraction of evidence supporting or contesting hypotheses from specific research papers. In this case, the focus is on [Hoang et al. (2016)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5533284/), which investigates the implications of AA on kidney cancer.

## Survey Summary & Hypothesis Extraction
**Survey Summary**: 
Extracted from a comprehensive survey on Aristolochic Acid, this summary encapsulates key findings from Hoang et al. (2016), highlighting that a cumulative ingestion of more than 250 mg of AA increases the risk of developing clear cell renal cell carcinoma (ccRCC) with an odds ratio (OR) of 1.25. Notably, a distinctive AA mutational signature was detected in the majority of the sequenced ccRCC exomes from patients exposed to AA. The VHL gene, crucial in many cell functions, was mutated in most cases studied.

**Hypothesis**: 
Does AA-induced DNA mutation cause renal carcinoma (RCC)?

## Study Aspect Decomposition
EvidenceBench dissects the Survey Summary into specific Study Aspects and aligns them with sentences from Hoang et al. (2016), providing per-sentence annotations:

1. **Increased Risk of ccRCC**
   - Cumulative ingestion of more than 250 mg of AA increased the risk of ccRCC (OR, 1.25).
   - Sentences reflecting this aspect:
     - "Cumulative ingestion of more than 250 mg of AA increased risk of ccRCC (OR, 1.25), and we detected dA-AL-I adducts in 76% of Taiwanese ccRCC patients." (Sentence 9)
     - "The results (Table 1) indicate an adjusted OR of 1.25 (1.004–1.547) for ccRCC in persons consuming more than 250 mg of AA during the period of 1997 to 2003." (Sentence 69)

2. **AA Mutational Signature**
   - A unique mutation pattern caused by AA was evident in the study.
   - Sentences reflecting this aspect:
     - "Whole-exome sequencing confirmed that the AA mutational signature was present in 6 of 10 ccRCC patients studied." (Sentence 163)

3. **Frequent Mutation of VHL Gene**
   - The VHL gene mutation was a common occurrence in the patients studied.
   - Sentences reflecting this aspect:
     - "VHL was the most frequently mutated driver gene (7/10 tumors) in our AA-exposed ccRCCs (Table 2)." (Sentence 106)

## System Sentence Retrieval
EvidenceBench's task is to retrieve sentences from the full text of Hoang et al. (2016) that are identified as carrying significant information about the Survey Summary. Here are the selected sentences, annotated with their corresponding Study Aspects:

- **Sentence 9**: Demonstrates the increased risk and presence of dA-AL-I adducts.
- **Sentence 69**: Provides statistical evidence of the increased risk.
- **Sentence 106**: Details the frequent mutation of the VHL gene.
- **Sentence 163**: Confirms the presence of the AA mutational signature.

