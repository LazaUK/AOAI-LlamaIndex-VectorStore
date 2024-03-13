# Retrieval-Augmented Generation (RAG) with LlamaIndex and Azure OpenAI
LlamaIndex is a popular framework for building RAG solutions, thanks to its abstractions of data connectors, indexes and processing engines. You will find a Jupyter notebook in this repo, that utilises LlamaIndex and Azure OpenAI models (GPT-4 and Embedding) to answer queries with pre-indexed local content.
> **Note:** content file used in this demo was borrowed from [Microsoft's Azure OpenAI + Azure AI Search demo](https://github.com/Azure-Samples/azure-search-openai-demo)

To build this demo, I used the latest version of LlamaIndex (**v0.10.19** at the time of writing). To upgrade your _llama-index_ Python package, please use the following pip command:
```
pip install --upgrade llama-index
```

## Table of contents:
- [Part 1: Configuring solution environment](https://github.com/LazaUK/AOAI-LlamaIndex-VectorStore#part-1-configuring-solution-environment)
- [Part 2: Indexing and retrieving content](https://github.com/LazaUK/AOAI-LlamaIndex-VectorStore#part-2-indexing-and-retrieving-content)

## Part 1: Configuring solution environment
1. To use Azure OpenAI backend, assign the API endpoint name, version and key, along with the Azure OpenAI deployment name of GPT and Embedding models to **OPENAI_API_BASE**, **OPENAI_API_KEY**, **OPENAI_API_VERSION**, **OPENAI_API_DEPLOY** (for GPT) and **OPENAI_API_DEPLOY_EMBED** (for Embedding) environment variables respectively.
![screenshot_1.1_environment](images/environment_var.png)
2. Install the required Python packages, by using the **pip** command and the provided requirements.txt file.
```
pip install -r requirements.txt
```

## Part 2: Indexing and retrieving content
1. Instantiate AzureOpenAI class with details of your GPT model (I'm using **GPT-4 Turbo** deployment).
``` Python
llm = AzureOpenAI(
    model = "gpt-4",
    deployment_name = AOAI_DEPLOYMENT1,
    api_key = AOAI_API_KEY,
    azure_endpoint = AOAI_API_BASE,
    api_version = AOAI_API_VERSION,
)
```
2. Instantiate AzureOpenAIEmbedding class with details of your Embedding model (I'm using **text-embedding-ada-002** deployment).
> **Note:** Assumptions are that both of your models are deployed in the same Azure OpenAI resource. If it's not the case, please adjust the values for Azure OpenAI endpoint and its API key.
``` Python
embed_model = AzureOpenAIEmbedding(
    model = "text-embedding-ada-002",
    deployment_name = AOAI_DEPLOYMENT2,
    api_key = AOAI_API_KEY,
    azure_endpoint = AOAI_API_BASE,
    api_version = AOAI_API_VERSION,
)
```
3. 
