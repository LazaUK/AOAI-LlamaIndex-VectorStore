# Retrieval-Augmented Generation (RAG) with LlamaIndex and Azure OpenAI
LlamaIndex is a popular framework for building RAG solutions, thanks to its abstractions of data connectors, indexes and processing engines. You will find a Jupyter notebook in this repo, that utilises LlamaIndex and Azure OpenAI models (GPT-4 and Embedding) to answer queries with pre-indexed local content.
> Note: content file used in this demo was borrowed from [Microsoft's Azure OpenAI + Azure AI Search demo](https://github.com/Azure-Samples/azure-search-openai-demo)

To build this demo, I used the latest version of LlamaIndex (v0.10.19 at the time of writing). To upgrade your _llama-index_ Python package, please use the following pip command:
```
pip install --upgrade llama-index
```
