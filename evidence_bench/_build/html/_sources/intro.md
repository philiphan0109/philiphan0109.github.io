# Evidence Bench

[![EvidenceBench Paper](https://img.shields.io/badge/Paper-NeurIPS-blue.svg?logo=read-the-docs&logoColor=white)](https://link_to_your_paper) [![LEI Lab](https://img.shields.io/badge/Lab%20Group-LEI%20Lab-blue.svg?logo=teams&logoColor=white)](https://lei.ucsd.edu/) [![GitHub](https://img.shields.io/badge/GitHub-EvidenceBench-blue.svg?logo=github&logoColor=white)](https://github.com/EvidenceBench/EvidenceBench)

## Task Formulation

We develop a pipeline for high-quality, sentence-by-sentence annotation of biomedical papers to find evidence for hypotheses. The pipeline, validated by human annotators, is used to evaluate various language models and retrieval systems on a benchmark of over 400 papers and 700k sentence judgments. Despite improvements, the best models still fall short of expert-level performance. This work aims to support the development of tools for automated evidence synthesis and hypothesis testing.

The EvidenceBench benchmark aims at identifying the most important pieces of information for or against a hypothesis within a paper. This sentence retrieval task is to retrieve the sentences which provide this evidence.

### Definitions

``Candidate Pool`` The full paper is presented as a list of sentences. This list of sentences is the Candidate Pool. 

``Study Aspect`` A study aspect is a single piece of information described in a paper. This could be an experimental outcome or a detail from study design.

``Source of Information`` A sentence is a paper is considered a source of information for a study aspect if it satisfies the following two criteria:

1. The content of the sentence implies most of the study aspect.
2. For any part of the study aspect that the sentence does not imply, the information must be deducible from the surrounding context.

``Hypothesis`` A hypothesis is a scientific generalization, expressible in one sentence. It should not be specific to one experiement. 

``Evidence Set`` The evidence set is the set of study aspects which provides evidence for or against a hypothesis. We use papers and the sentences in them to curate the evidence set.

### Evidence Retrieval @ K

Our primary task is Evidence Retrieval @ K (``ER @ K``)