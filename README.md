# OllamaRAGApp

Key Technologies

Streamlit: For building an intuitive and interactive user interface.

LangChain: Leveraging community components for efficient document handling and question answering.

Ollama: A tool that facilitates running large language models (LLMs) locally.

Mistral 7B: An open-source model used for text embeddings and retrieval-based question answering.

nomic-embed-text Model: A high-performing open embedding model with a large token context window that outperforms OpenAI embeddings.

Why Use Ollama?

Ollama is an excellent tool for running open-source LLMs locally, such as Mistral and Llama 2. 
Here are some reasons why Ollama stands out:

Unified Package: Ollama bundles model weights, configurations, and datasets into a single, manageable package known as a Model file.

Versatility: It supports a variety of LLMs, including LLaMA-2, uncensored LLaMA, CodeLLaMA, Falcon, Mistral, Vicuna model, WizardCoder, and Wizard uncensored.

Security: By running LLMs locally, Ollama ensures that your data remains safe and secure.


App Overview

On a fundamental level, the workflow of the app is remarkably straightforward:

User Input: A user submits a list of URLs (one per line) and enters a question.

Content Fetching: The app processes the input, fetching the content from the provided URLs.

Content Chunking: The text content is split into manageable chunks.

Embeddings Creation: These chunks are converted into embeddings using the nomic-embed-text model and stored in a vector database (Chroma).

Question Processing: The user’s question is processed through a Retrieval-Augmented Generation (RAG) pipeline, which retrieves relevant document sections and generates an answer using the Mistral 7B model.

![Ollam-RAG](https://github.com/user-attachments/assets/d610dbdf-e77f-4aff-9500-3cbc884bf0c5)


## How to Use This Repository

## Step 1: Download and Install Ollama

## Step 2: install ollama and Pull the Models

Follow these steps to pull the necessary models:

Download the Model: Use the command        ollama run mistral & ollama run nomic-embed-text  
Fetch Available LLM Model: Use             ollama pull mistral & ollama pull nomic-embed-text.

## Step 3: Create and activate Conda envirnoment

```bash
conda create -p ollamaRagenv python=3.8 -y
```

## Step 4: Install Dependencies

```bash
source activate ./ollamaRagenv
```
## Step 5: Run the application using Streamlit:

```bash
streamlit run app.py
```

## How to Use

### Question

- Text area 1: Copy and paste the URLs you want searched based on.
- Write your query in question section.
- Click on Query Documents.

## Using a Different Model

If you want to use a different model, pull it using: `ollama run <model>`
Then, modify the code line:
`python model_local = Ollama(model="mistral")`
to
`python model_local = Ollama(model="new-model")`

## Based on This Tutorial

This guide is based on the tutorial provided by Sri Laxmi Beapc on LinkedIn:

[How to Build a RAG Chatbot Using Ollama to Serve LLMs Locally](https://www.linkedin.com/pulse/how-build-rag-chatbot-using-ollama-serve-llms-locally-sri-laxmi-beapc?utm_source=share&utm_medium=member_ios&utm_campaign=share_via)
