# Task Formulation

## Definitions

``Candidate Pool`` The full paper is presented as a list of sentences. This list of sentences is the Candidate Pool. 

``Study Aspect`` A study aspect is a single piece of information described in a paper. This could be an experimental outcome or a detail from study design.

``Source of Information`` A sentence is a paper is considered a source of information for a study aspect if it satisfies the following two criteria:

1. The content of the sentence implies most of the study aspect.
2. For any part of the study aspect that the sentence does not imply, the information must be deducible from the surrounding context.

``Hypothesis`` A hypothesis is a scientific generalization, expressible in one sentence. It should not be specific to one experiement. 

``Evidence Set`` The evidence set is the set of study aspects which provides evidence for or against a hypothesis. We use papers and the sentences in them to curate the evidence set.

## Evidence Retrieval @ K

Our primary task is Evidence Retrieval @ K (``ER @ K``) - to find the k sentences from the candidate pool (paper) which provide evidence for or against the hypothesis. The retrieved sentences are then evaluated against the evidence set, which contains the ground-truth study aspects that provide evidence for or against the hypothesis.

The goal is for the retrieved sentences to be sources of information for study aspects in the evidence set. The system does not have access to the evidence set, it is only for evaluation.

The second version of a task is that only study aspects delated to the results and analyses are considered. Those related to background and methodolody are omitted from the evidence set. This is ``Result-ER @ K`` and it provides a more targeted evaluation of the system's ability to identify the most important evidence.