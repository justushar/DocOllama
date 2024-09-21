# DocOllama - Private Chat with Your Documents

> Completely local RAG with chat UI

## Installation

Clone the repo:

```sh
git clone git@github.com:justushar/DocOllama.git
cd DocOllama
```

Install the dependencies:

```sh
pip install -r requirements.txt
```

Fetch your LLM (llama3.1 by default):

```sh
ollama pull llama3.1:8b
```

Run the Ollama server

```sh
ollama serve
```

Start DocOllama:

```sh
streamlit run app.py
```

## Architecture

<a href="https://www.mlexpert.io/bootcamp" target="_blank">
  <img src="https://raw.githubusercontent.com/curiousily/ragbase/master/.github/architecture.png">
</a>

### Ingestor

Extracts text from PDF documents and creates chunks (using semantic and character splitter) that are stored in a vector databse

### Retriever

Given a query, searches for similar documents, reranks the result and applies LLM chain filter before returning the response.

### QA Chain

Combines the LLM with the retriever to answer a given user question

## Tech Stack

- [Ollama](https://ollama.com/) - run local LLM
- [LangChain](https://www.langchain.com/) - build LLM-powered apps
- [Qdrant](https://qdrant.tech/) - vector search/database
- [FlashRank](https://github.com/PrithivirajDamodaran/FlashRank) - fast reranking
- [FastEmbed](https://qdrant.github.io/fastembed/) - lightweight and fast embedding generation
- [Streamlit](https://streamlit.io/) - build UI for data apps
- [PDFium](https://pdfium.googlesource.com/pdfium/) - PDF processing and text extraction
