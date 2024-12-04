# Context-Aware Plagiarism Advisory Tool
Evelyn Yee (CS 329T Final Project)

## Poster:
![project poster](figures/poster.png)

## Project Proposal
- Domain: Education
- Goal: Build a system to advise instructors and provide evidence for/against plagiarism in student works.
    - Difficult false positives: critique, citing, reference
    - Difficult false negatives: paraphrasing, summary, misquoting/misattribution
- System:
    1. **Retrieve** relevant documents from the corpus (e.g. vector search, string matching)
    1. **Reason** over text+context documents with LLM (RAG)
    1. **Identify** textual relationships
        - Ground claims in passages from new document and context
    1. Confidence estimation?
- Trustworthiness Principles:
    - **Grounding:** Each claim in the plagiarism analysis will be forced to reference at least one specific quote/passage in the new document and at least one of the context documents.
    - **Interpretability:** Provide to users a report containing a) potential plagiarism sources and b) a detailed assessment from the LLM, containing references to the source documents and the student's submission and ending with a single label of the text ("plagiarized," "related," or "unrelated"). The LLM CoT transcript/trace allows users (instructors) to understand and self-assess the label.

- Data: [PlagBench](https://arxiv.org/abs/2406.16288v1) Eval Set (accessed directly from jooyoung lee, since the full dataset hasn't been publicly released yet)
    - 405 plagiarism pairs
        - 135 verbatim plagiarism
        - 135 paraphrasing plagiarism
        - 135 summarization plagiarism
    - 405 non-plagiarism, related document pairs

    I have partitioned the dataset into a 70/15/15 train/validation/test split, with each split having the same proportion of each plagiarism label (i.e. 16.67% verbatim, 16.67% paraphrasing, 16.67% summary, 50% negative).

## Repo Description
Currently, my code and analysis for this project is all in the `plagiarism.ipynb` notebook. Later, I plan on converting this code into .py files for better reproducibility and creating a demo page to display some example results.

The poster and relevant figures are in the `figures` folder.