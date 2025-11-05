# RAG-QA-Agent

Project: RAG-Based Q&A AI Agent using LangGraph + ChromaDB
Objective
This project implements a Retrieval-Augmented Generation (RAG) based AI Agent that answers user questions using a small knowledge base.
The agent uses a LangGraph workflow with four nodes:


plan → interpret user query


retrieve → fetch relevant documents using Vector DB


answer → generate response using an LLM with context


reflect → validate relevance of generated answer


The entire pipeline runs inside a single Google Colab notebook.

 Tech Stack
ComponentTool UsedVector DBChromaDBEmbeddingsHuggingFace (MiniLM)LLMHuggingFace GPT-2FrameworkLangChain + LangGraphRuntimeGoogle Colab / Python 3

 Features
 RAG-based answer generation
 Retrieval using local ChromaDB
 Small knowledge base (data.txt)
 Reflection step to check relevance
 Full logging of plan → retrieve → answer → reflect steps

** How to Run (Google Colab Setup)
Step 1: Install Dependencies
!pip install langchain langgraph chromadb sentence-transformers transformers

Step 2: Run Notebook


Upload notebook to Google Colab


Run all cells in order


When prompted, type your question
Example:
What are the benefits of renewable energy?




** Folder Structure
├── main.ipynb          # Main notebook
├── data.txt            # Knowledge base text
├── requirements.txt    # Required Python libraries
└── README.md           # Project explanation


** How the Agent Works


plan node


Receives user query


Decides that retrieval is required




retrieve node


Converts query to embedding


Performs similarity search on ChromaDB


Retrieves top-k matching text chunks




answer node


Combines query + retrieved context


Uses GPT-2 model to generate response




reflect node


Checks whether generated answer is relevant to query


Outputs a simple relevance score (0 or 1)





** Example Output
[PLAN] Received Query: What are benefits of renewable energy?
[RETRIEVE] Retrieved Context: ...
[ANSWER] Generated Answer: ...
[REFLECT] Score: 1


** Challenges Faced
1]Version compatibility between LangChain, LangGraph, and ChromaDB
2]Chunk size tuning for accurate retrieval
3]Preventing hallucination in GPT-2 output
4]Passing state correctly between graph nodes




Task: Interview Task 1 – RAG Q&A AI Agent



✅ This README satisfies all requirements for submission ✅
If you want, I can also create a short 2-paragraph report to attach with the project. Want me to include that as well?
