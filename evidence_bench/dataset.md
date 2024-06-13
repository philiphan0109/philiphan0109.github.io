# Dataset Structure

```{note} Evidence Bench's train, dev, and test split all have the same structure.
```

Each data instance (stored in a JSON) has the following features:

- ```hypothesis```: the biomedical hypothesis in string format
- ```paper_as_candidate_pool```: an ordered tuple of strings. Each string is one sentence from the paper. This is the candidate pool for all of the evidence retrieval tasks.
- ```aspect_list_ids```: a list of strings. Each string is an id for an aspect related to the study's results.
- ```aspect2sentence_indices```: a dictionary that maps from each aspect to all sentence indices that are sources of information for that aspect.
- ```sentence_index2aspects```: a dictionary that maps from each sentence index to all aspects that this sentence is a source of information for.
- ```evidence_retrieval_at_optimal_evaluation```: A dictionary that contains informa- tion for evaluating a model’s performance on the task Evidence Retrieval @Optimal.
    - **optimal**: A positive integer, which is the smallest number of sentences needed to cover all study aspects.
    - **one_selection_of_sentences**: a list of sentence indices, containing the smallest number of sentences needed to cover all aspects. Note, there are potentially other lists of sentences of the same size which cover all aspects.
    - **covered_aspects**: the list of aspects that are covered, which is all aspects in this case.
- `evidence_retrieval_at_10_evaluation`: A dictionary that contains information for evaluating a model’s performance on the task Evidence Retrieval @10.
    - **one_selection_of_sentences**: a list of 10 sentence indices. This list covers the maximum number of aspects which can be covered by 10 sentences.
    - **covered_aspects**: the list of aspects that are covered, which may be fewer than all aspects.
- ```results_evidence_retrieval_at_optimal_evaluation```: A dictionary that contains the information for evaluating a model’s performance on the task Results Evidence Retrieval @Optimal. The structure is similar to evidence_retrieval_at_optimal_evaluation.
- `results_evidence_retrieval_at_5_evaluation`: A dictionary that contains the nec- essary information for evaluating a model’s performance on the task Results Evidence Retrieval @5. The structure is similar to evidence_retrieval_at_10_evaluation.
- `sentence_types_in_candidate_pool`: a tuple of strings. Each string is a sentence type. There are three possible sentence types: **section_name**, **abstract**, and **normal_paragraph**. For example, if the third string is ’abstract’, that means the third sentence comes from the abstract.
- `paper_id`: the id of the paper used as the candidate pool.
