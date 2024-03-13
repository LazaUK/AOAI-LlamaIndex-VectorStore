# Retrieval-Augmented Generation (RAG) with LlamaIndex and Azure OpenAI
LlamaIndex is a popular framework for building RAG solutions, thanks to its abstractions of data connectors, indexes and processing engines. You will find a Jupyter notebook in this repo, that utilises LlamaIndex and Azure OpenAI models (GPT-4 and Embedding) to answer queries with pre-indexed local content.
> Note: content file used in this demo was borrowed from [Microsoft's Azure OpenAI + Azure AI Search demo](https://github.com/Azure-Samples/azure-search-openai-demo)

To build this demo, I used the latest version of LlamaIndex (**v0.10.19** at the time of writing). To upgrade your _llama-index_ Python package, please use the following pip command:
```
pip install --upgrade llama-index
```

## Table of contents:
- [Part 1: Configuring solution environment](https://github.com/LazaUK/AOAI-LlamaIndex-VectorStore#part-1-configuring-solution-environment)
- [Part 2: Indexing and retrieving content](https://github.com/LazaUK/AOAI-LlamaIndex-VectorStore#part-2-indexing-and-retrieving-content)

## Part 1: Configuring solution environment
1. To use Azure OpenAI backend, assign the API endpoint name, version and key, along with the Azure OpenAI deployment name of GPT and Embedding models to **OPENAI_API_BASE**, **OPENAI_API_VERSION**, **OPENAI_API_KEY**, **AOAI_DEPLOYMENT1** (for GPT) and **AOAI_DEPLOYMENT2** (for Embedding) environment variables respectively.
![screenshot_1.1_environment](images/environment_var.png)
2. Install the required Python packages, by using the **pip** command and the provided requirements.txt file.
```
pip install -r requirements.txt
```

## Part 2: Indexing and retrieving content
