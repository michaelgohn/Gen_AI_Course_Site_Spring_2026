# Prompt Engineering Project 

## What this project is
You will build and evaluate an LLM-powered assistant using prompting techniques and a RAG pipeline. The project has two main parts:

- **Part 1: Prompting + LLM-as-a-judge** (completed last week)
- **Part 2: RAG + prompt techniques + LLM-as-a-judge** 


## Part 2: RAG + Prompt Techniques + LLM-as-a-Judge

This part builds a code-documentation Q&A bot using a small RAG pipeline. It answers questions about **Python**, **Java**, and **JavaScript** using documentation PDFs.

We will be using ChromaDB for this. Take a look at this page to learn more about it: https://docs.trychroma.com/docs/overview/getting-started

### What happens in the pipeline
0. **Build Vector Collections**: Initial check to see if the vector collections exist, if they don't, build them.
1. **Routing**: A POML prompt classifies the question based on what programming language it is refering to.
2. **Retrieval**: ChromaDB searches the vector collection corresponding to that programming language for relevant chunks.
3. **Answering**: A POML prompt generates an answer using the retrieved context from the documentation PDFs, and the LLM call is made through LangChain (ChatGroq).
4. **Comparison (optional)**: If the comparison option was selected, use model graded evaluation to compare the responses.

### Key folders and files
- `part_2_skeleton/ingest_files/` — PDFs used for retrieval
- `part_2_skeleton/rag_ingestion/ingest_documents.py` — builds the ChromaDB vector store
- `part_2_skeleton/chatbot/main.py` — CLI entry point and judge evaluation
- `part_2_skeleton/chatbot/rag_pipeline.py` — routing, retrieval, generation, comparisons
- `part_2_skeleton/chatbot/prompts/` — POML prompt templates (routing, answering, judging)

---

## Setup

Make sure you have a `.env` file with your Groq API key in your directory for this class (used by LangChain's ChatGroq).
```
GROQ_API_KEY=your_api_key_here
```

Install Python dependencies:

```bash
pip install -r Gen_AI_Course_Site_Spring_2026/individual_project/part_2_skeleton/requirements.txt
```

---

## Running Part 2
1. **Build the vector store** (can either run this manually, or call it when you run the main.py file):
   ```bash
   python Gen_AI_Course_Site_Spring_2026/individual_project/part_2_skeleton/rag_ingestion/ingest_documents.py
   ```

2. **Run the CLI**:
   ```bash
   python Gen_AI_Course_Site_Spring_2026/individual_project/part_2_skeleton/chatbot/main.py
   ```

3. **Choose a mode**:
   - Single Model & Single Prompting Technique
   - Compare Multiple Models using Single Prompting Technique
   - Compare Multiple Prompting Techniques using single Model

---

## What you need to do:
- Edit prompt templates in `part_2_skeleton/chatbot/prompts/answer.poml`
- Adjust routing prompt / logic in `part_2_skeleton/chatbot/prompts/route.poml`
- Modify which models are compared in `part_2_skeleton/chatbot/rag_pipeline.py`

---

## Deliverables
- Updated prompts (zero-shot, few-shot, chain-of-thought)
- Evidence of model or technique comparison results
- Short PDF write-up explaining what you did and any takeaways you have.

If you prefer to work from your implementation of part 1, feel free to do so. Otherwise you can directly edit this repo.


## Ways to improve the system
#### If you are able to finish the requirements and want to take things further, here are a few options:
- Right now the routing judge POML prompts only use a single prompting technique. You could add multiple prompting technique options and compare results.
- Try out different retrieval methods. We will cover some of these later in the class, but if you want to give them a try you can. Do some research on ChromaDBs options for cosine similarity, L2 Distance, keyword, and hybrid search.
- Implement multi-turn conversations with chat memory.
