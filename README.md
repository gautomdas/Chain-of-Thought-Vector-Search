# Chain-of-Thought Vector Search

This project explores the potential of employing a triple-style vector search approach to assist large language models (LLMs) in querying relevant and causally-linked information more efficiently, thereby enhancing their ability to answer complex questions. As a proof-of-concept, this three-day project uses a subset of the StrategyQA dataset for testing, which provides both a rigorous set of questions that require complex reasoning and a massive dataset of Wikipedia paragraphs from which all the questions are drawn.

The repository contains six Jupyter notebooks that detail each step of the project from data collection, processing, and finally demonstrating a simple query algorithm.

## Files

### `0_get_questions.ipynb`

This is an exploratory notebook that provides an overview of the types of questions available in the dataset. It aims to understand the structure and complexity of the questions to identify a subset of questions suitable for the experiment.

### `1_encode_questions.ipynb`

This notebook focuses on embedding the questions and clustering them. This step is necessary to identify a manageable and representative subset of questions to answer using the proposed chain-of-thought vector search approach.

### `2_collect_cluster_subset_data.ipynb`

Once a subset of questions has been identified, this notebook collects the corresponding paragraph data that will be used to answer these questions. This data will be transformed into causally-linked triples using the GPT model in the next step.

### `3_gpt_local.ipynb`

In this notebook, the GPT model is used to convert the paragraph data into causally linked triples. These triples, formed by breaking down complex paragraphs, are expected to allow LLMs to answer more complex questions efficiently.

### `4_processing.ipynb`

The triples generated in the previous step are then uploaded to the QDrant vector database in this step. This process prepares the data for the query algorithm that will be demonstrated in the final notebook.

### `5_query_algorithm.ipynb`

The final notebook in this repository demonstrates a simple query algorithm using the causally-linked triples stored in the QDrant vector database. The effectiveness of this approach in answering complex questions is evaluated in this step.

## Hypothesis

By breaking paragraphs/context down into causally linked triples, it's hypothesized that LLMs will be able to answer more complex questions more efficiently. This project is a Minimum Viable Product (MVP) demonstration of the potential of the nearest neighbors chain-of-thought search methodology.

This project is experimental, and while it has shown promising results on a small subset of questions, further work is required to scale and optimize the model for larger datasets and more complex queries.

## Dataset

The StrategyQA dataset was chosen for testing because it offers a robust set of questions that require complex reasoning and a massive dataset of approximately 36 million Wikipedia paragraphs. These factors make it an ideal candidate for the chain-of-thought vector search methodology.

Please note that the MVP was built using a much smaller subset of the questions and paragraphs due to the time constraint (3 days) for this project. The code, however, can be adapted to larger sets or different data sources.

## Requirements

To replicate this experiment, you'll need Python, Jupyter Notebook, and access to the StrategyQA dataset. Please ensure you have the necessary libraries installed, including Numpy, Pandas, PyTorch, transformers (for GPT), and QDrant.
