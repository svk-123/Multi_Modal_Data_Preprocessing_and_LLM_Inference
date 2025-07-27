# 📘 Teaching Science Book/Chapter to LLM for QA

This repository (WIP) contains a framework for extracting, structuring, and leveraging textbook content to enhance question-answering (QA) performance in a small Language Model (LLM). The project is divided into four phases:

- Data processing  
- LLM evaluation  
- Local deployment  
- Cloud automation

---

## 📚 Table of Contents

- [Phase 1: Data Processing](#phase-1-data-processing)
- [Phase 2: Evaluating LLM Performance](#phase-2-evaluating-llm-performance)
- [Phase 3: Local Deployment and Automation](#phase-3-local/cloud-deployment-and-automation)

---

## Phase 1: Data Processing

### Extracting and Structuring Textbook Content

The textbook is in PDF format and contains multi-modal content (text, images, tables, and equations). We use the `unstructured` library for efficient extraction and preprocessing.

#### Extracting Data from PDF

- Use `unstructured` to partition and extract structured text, tables, images, and equations.
- Identify different content types and store them separately for further processing.

#### Preprocessing & Structuring Data

- Convert extracted content into structured formats such as JSON, Markdown, or a database.
- Format tables and figures separately to ensure proper retrieval during inference.
- Perform OCR on images if needed to extract embedded text.
- Store textbook embeddings in a vector database for retrieval-based answering.

---

## Phase 2: Evaluating LLM Performance

We evaluate a small LLM using three approaches:

### Baseline - Direct Question Answering

- Directly feed textbook-related questions to the LLM without additional knowledge.
- Evaluate its accuracy and limitations.

### Fine-tuning for Domain Adaptation

- Convert extracted textbook content into a structured Q&A dataset.
- Experiment with full fine-tuning and PEFT (Parameter-Efficient Fine-Tuning).
- Measure accuracy improvements compared to the baseline.

### Retrieval-Augmented Generation (RAG) Implementation

- Convert textbook content into vector embeddings.
- Implement similarity search to retrieve relevant textbook sections during inference.
- Use `LangChain` or `LlamaIndex` to integrate the RAG pipeline.
- Evaluate improvements in response accuracy.

---

## Phase 3: Local/Cloud Deployment and Automation
- In progress...


