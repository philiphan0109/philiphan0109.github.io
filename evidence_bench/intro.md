# Evidence Bench

[![EvidenceBench Paper](https://img.shields.io/badge/Paper-blue.svg?logo=read-the-docs&logoColor=white)](https://link_to_your_paper) [![LEI Lab](https://img.shields.io/badge/Lab%20Group-LEI%20Lab-blue.svg?logo=teams&logoColor=white)](https://lei.ucsd.edu/) [![GitHub](https://img.shields.io/badge/GitHub-EvidenceBench-blue.svg?logo=github&logoColor=white)](https://github.com/EvidenceBench/EvidenceBench)

## Introduction

Welcome to **EvidenceBench**! Our goal is to provide a robust benchmark for retrieving evidence from biomedical papers that provides evidence for or against scientific hypotheses. Our pipeline involves high-quality, sentence-by-sentence annotations, validated by human experts, across over 400 papers and 700k sentence judgments. 


![Figure 1](_figs/fig1.png)

<p style="text-align: left; font-size: smaller; line-height: 1.2;">Figure 1: In EvidenceBench, a model sees a hypothesis, and the full sequence of sentences from a paper as a candidate pool. The goal is to select sentences that provide evidence for or against the hypothesis. The retrieved sentences are compared to ground-truth study aspects, collected from literature surveys, which identify relevant evidence from the paper. In this case, the model selects S9, S69, and S106 as the set of retrieved sentences. However, these 3 sentences only cover study aspects 1, 3, and 4. Aspect 3 is missed, resulting in 75% Aspect Recall.</p>
