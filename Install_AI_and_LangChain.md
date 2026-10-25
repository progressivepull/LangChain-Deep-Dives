If you want to run an AI model locally on your computer and use it with
**LangChain**, here is one of the easiest setups.

# **Option 1: Use Ollama + LangChain (Recommended)**

## **Step 1: Install Ollama**

Download and install Ollama:

[Ollama Official Website](https://ollama.com)

**Download Ollama**     
Get started by installing Ollama, or have your agent install it for you

```
irm https://ollama.com/install.ps1 | iex
```



After installation, open a terminal and pull a model:

```shell
ollama pull llama3.2
```

Or:

```shell
ollama pull mistral
```

Run the model:

```shell
ollama run llama3.2
```

Test the model is running

```shell
>>> What is the capital of Ohio?
The capital of Ohio is Columbus.

>>> Send a message (/? for help)
```

## **Step 2: Install Python**

Verify Python is installed:

**Shell**

**python \--version**

If not, download it from:

https://python.org

**[Step 3: Create a Virtual Environment]{.underline}**

**Shell**

**python -m venv venv**

Activate it:

**Windows**

**Shell**

**venv\\Scripts\\activate**

**Linux/Mac**

**Shell**

**source venv/bin/activate**

**[Step 4: Install LangChain]{.underline}**

**Shell**

**pip install langchain langchain-community langchain-ollama**

**[Step 5: Test LangChain with Ollama]{.underline}**

Create test.py:

Python

from langchain_ollama import OllamaLLM

 

llm = OllamaLLM(model=\"llama3.2\")

 

response = llm.invoke(\"Explain LangChain in simple terms.\")

print(response)

Run it:

**Shell**

**python test.py**

**[Step 6: Use Documents with LangChain]{.underline}**

Install additional packages:

Shell

pip install faiss-cpu pypdf sentence-transformers

Basic RAG (Retrieval-Augmented Generation) workflow:

Plain Text

PDF Files

↓

Load documents

↓

Create embeddings

↓

Store in FAISS

↓

LangChain retrieves relevant content

↓

Local AI answers questions

**Hardware Recommendations**

  -----------------------
  **Model**     **RAM**
  ------------- ---------
  Llama 3.2 3B  8 GB

  Llama 3.1 8B  16 GB

  Mistral 7B    16 GB

  DeepSeek-R1   16-32 GB
  7B            
  -----------------------

**With NVIDIA GPU**

Install CUDA-enabled drivers. Ollama will automatically use the GPU when
available.

**Alternative Local AI Tools**

- **Ollama** (easiest)

- **LM Studio** (GUI based)

- **GPT4All**

- **Jan AI**

- **text-generation-webui**

For most people, **Ollama + LangChain + Llama 3.2** is the quickest and
simplest way to get a local AI assistant running on a Windows PC.

[Context](./README.md)
