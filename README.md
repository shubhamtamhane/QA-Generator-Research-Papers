# QA-Generator-Research-Papers


## I. Abstract

Researchers often face challenges comprehending entire research papers in a single pass. The three-pass approach, although efficient, is time-consuming. This project proposes a solution using a Question-Answering (QA) model with search and extract behavior to summarize research papers more efficiently. The model is based on the T5 pre-trained model, fine-tuned on the QASPER dataset modified using OpenAI.

## II. Introduction

Understanding research papers can be simplified by compressing them into a question-answer format. The project aims to design and develop a Dynamic QA model for research papers. By extracting relevant information and generating questions and answers, the model facilitates quicker comprehension. Additionally, the model is trained to answer user-generated questions related to the paper.

## III. Dataset

### A. QASPER Dataset

QASPER is a QA dataset over Natural Language Processing papers, containing 5,049 questions over 1,585 papers. Annotated by NLP practitioners, each paper has an average of 3.2 questions, seeking information from the full text. The dataset presents challenges like multiple evidence snippets and dependence on tables or figures.

### B. QASPER Data Cleaning

The QASPER dataset underwent cleaning to prepare it for model input. Unanswerable questions and missing values were removed. Selected evidence snippets were used as answers, with prioritization given to text over figures and tables.

### C. OpenAI Integration with QASPER

To address limitations, OpenAI's API services were integrated with QASPER. Sections from QASPER were passed to OpenAI's Chat Completion API to generate question-answer pairs. The resulting dataset was used for fine-tuning the model.

## IV. Implementation

### A. Model

The model is based on the T5 transformer architecture, trained using supervised and unsupervised learning. Fine-tuning involves using transfer learning on T5 and RoBERTa for question generation and answer generation. Evaluation metrics include BLEU score, ROUGE, and QAEval.

### B. Question Generation on QASPER

Attempts to train the T5 model solely on QASPER were limited due to dataset constraints. Integration with OpenAI's API services was essential for improved outputs.

### C. Question Generation on QASPER with OpenAI

A dataset of 20,153 question-answer pairs was generated using OpenAI's Chat Completion API with the T5Model. The model was fine-tuned for question generation, utilizing the "ask question" prefix.

### D. Answer Generation

Answer generation used the T5Model with the "question:" prefix. Sections from research papers served as context for answer generation.

## VI. Limitation

Limited computational resources constrained the use of advanced T5 models. The OpenAI API generated abstractive answers, making exact answer position determination challenging. Evaluating generated questions relied on human assessment. The accuracy of generated answers may lack precision in certain contexts.

## VII. Future Work

Future work aims to support user-generated queries and provide summarization of entire papers. Techniques such as sentence or paragraph indexing may be explored to specify the location of extracted content.
