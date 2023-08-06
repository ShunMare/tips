---
title: LlamaIndex Overview
published: true
description: description
tags: LlamaIndex, OpenAI
---

## LlamaIndex
LlamaIndex is a data framework designed to fully leverage LLMs (Language Models) pre-trained on vast amounts of public data.

## Why LlamaIndex?
LLMs offer a natural language interface between humans and inferred data. Most models are pre-trained on vast amounts of publicly available data such as Wikipedia, mailing lists, textbooks, and source code. LlamaIndex plays a pivotal role in supplementing these models with private or domain-specific data.

## How LlamaIndex Helps?
- **Data Connectors**: Imports existing data from its native source or format, including APIs, PDFs, SQL, etc.
- **Data Index**: Structures data into a format that's easy for LLMs to consume.
- **Engine**: Provides natural language access to the data.

## Who is LlamaIndex for?
LlamaIndex offers tools for beginners, advanced users, and everyone in between.

## Starting with LlamaIndex
To start using LlamaIndex, simply install it using pip.
Full installation instructions and starter tutorials are also provided.
```bash
pip install llama-index
```
## Ecosystem
You can download or contribute to LlamaIndex at:
- Github
- PyPi

Join the LlamaIndex community for assistance or to suggest features:
- Twitter
- Discord

There are related projects such as LlamaHub and LlamaLab.

## Quick Code Guide
1. Setting up OpenAI API key:
    ```python
    import os
    os.environ["OPENAI_API_KEY"] = 'YOUR_OPENAI_API_KEY'
    ```

2. Loading data and creating index:
    ```python
    from llama_index import VectorStoreIndex, SimpleDirectoryReader
    documents = SimpleDirectoryReader('data').load_data()
    index = VectorStoreIndex.from_documents(documents)
    ```

3. Executing a query:
    ```python
    query_engine = index.as_query_engine()
    query_engine.query("<question_text>?")
    ```

4. Persisting data:
    ```python
    index.storage_context.persist()
    ```

5. Loading data from disk:
    ```python
    from llama_index import StorageContext, load_index_from_storage
    storage_context = StorageContext.from_defaults(persist_dir='./storage')
    index = load_index_from_storage(storage_context)
    ```

Dependencies
The main third-party package requirements for LlamaIndex are `tiktoken`, `openai`, and `langchain`. All requirements can be installed with:
```bash
pip install -r requirements.txt
```