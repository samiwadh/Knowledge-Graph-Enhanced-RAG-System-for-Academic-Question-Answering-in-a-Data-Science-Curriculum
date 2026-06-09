# Knowledge Graph-Enhanced Retrieval-Augmented Generation for Academic Question Answering

A curriculum-specific question answering system built for a Data Science program at the University of Milano-Bicocca.  
The project combines **Retrieval-Augmented Generation (RAG)** with a lightweight **Knowledge Graph** to improve answer quality for academic questions based on course PDFs.

## Project Overview

Large language models can answer fluently, but they may not always stay grounded in the source material.  
This project addresses that issue by retrieving relevant lecture chunks from course PDFs and enriching them with graph-based curriculum context.

The system is designed for three course areas:

- Machine Learning
- Data Management
- Data Semantics

It compares:

- **Baseline RAG**: answers based only on retrieved text chunks.
- **KG-Enhanced RAG**: answers based on retrieved chunks plus knowledge graph context.

## Main Idea

The goal is to support academic question answering in a curriculum setting where relations between concepts matter.  
For example, some questions are not answered well by simple semantic search alone because they depend on connections such as:

- which course teaches a topic,
- which concepts are related,
- and which ideas are prerequisites for others.

A lightweight knowledge graph helps add this missing structure.

## Features

- PDF ingestion from course folders.
- Text extraction and chunking.
- Sentence-BERT embeddings for semantic retrieval.
- ChromaDB vector store for similarity search.
- Lightweight JSON/RDF-style knowledge graph.
- Baseline RAG vs KG-enhanced RAG comparison.
- Manual evaluation on curated academic questions.
- Visualization of results.

## Project Structure

```bash
├── data/
│   ├── machine_learning/
│   ├── data_management/
│   └── data_semantics/
├── outputs/
│   ├── all_chunks.json
│   ├── evaluation_results.csv
│   └── evaluation_chart.png
├── kg_files/
│   ├── academic_kg.ttl
│   └── kg_index.json
├── chroma_db/
├── notebook.ipynb
└── README.md
```

## Workflow

1. Create the folder structure.
2. Count and verify available PDF files.
3. Extract text from lecture PDFs.
4. Split the text into overlapping chunks.
5. Embed chunks using Sentence-BERT.
6. Store embeddings in ChromaDB.
7. Build a lightweight knowledge graph.
8. Run baseline RAG and KG-enhanced RAG.
9. Evaluate answers manually.
10. Visualize the comparison.

## Results

The evaluation showed that KG-enhanced RAG performed better overall than the baseline system on the curated curriculum questions.  
The graph was especially helpful for relation-heavy questions, while baseline retrieval remained effective for direct factual questions.

## Responsible AI

Generative AI tools were used only for writing support, clarification, and editing assistance.  
All project design, implementation, evaluation, and final interpretation were reviewed and completed by the author.  
A Responsible AI section is included in the report for transparency.

## Technologies Used

- Python
- PyMuPDF
- Sentence-Transformers
- ChromaDB
- RDFLib
- NetworkX
- Matplotlib
- Ollama / local LLM pipeline

## Future Work

Possible improvements include:

- expanding the knowledge graph,
- adding lexical retrieval,
- using graph-guided reranking,
- improving evaluation with a larger question set,
- and testing more advanced GraphRAG strategies.

## Author

Abdul Sami  
University of Milano-Bicocca
