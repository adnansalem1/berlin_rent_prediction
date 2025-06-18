[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/E9H7oBic)
# 5. Assignment: LLMs and rag

## Prerequisites

1. Create a venv by running `python -m venv venv`
1. Activate (`source venv/bin/activate` on WSL/Linux) the virutal environment.
	
	On Windows with activate the environment with PowerShell:
	```powershell
	.\venv\Scripts\Activate.ps1
	```
	or on Windows with Command Prompt:
	```cmd
	.\venv\Scripts\activate.bat
	```
1. install all requirements for the exercises (`pip install -r requirements.txt`). 
If you need additional or different dependencies, feel free to update the file.


Every assignment should be completed in a Jupyter notebook. Start the jupyter server
with the following command:
```bash
jupyter notebook
```

## Tasks

The dataset is taken from: [https://huggingface.co/datasets/rajpurkar/squad](https://huggingface.co/datasets/rajpurkar/squad)


More specifically
1. Use the `google/bert_uncased_L-2_H-128_A-2` transformer model and vicinity vector index to vectorize and index the title and text (the title needs to be split into tokens by `_`). Save the index to disk (don't add it to the repo)
1. Load the vector index
1. Write a prompt template that takes a random question from the data, and uses retrieved passages to answer it
1. As an SLM (Small Language Model), we use `Qwen/Qwen3-0.6B` with transformers library
1. To test your RAG pipeline, pick a set of questions for the same document (by document title), retrieve the most relevant text, and let the SLM generate the answer. Then compare and how many cases the SLM actually includes the answer snippet in the generated text (the answer should be the taken from the `answers` column, use the first element of `"text"` key). Report the answer accuracy as number of answers that include the answer snippted over all answers generated.
