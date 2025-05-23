# 📘 Teaching Science Book/Chapter to LLM for QA

*Initially, test with single chapter – once matured, add larger content.*

This repository (WIP) contains a framework for extracting, structuring, and leveraging textbook content to enhance question-answering (QA) performance in a small Language Model (LLM). The project is divided into four phases:

- Data processing  
- LLM evaluation  
- Local deployment  
- Cloud automation

---

## 📚 Table of Contents

- [Phase 1: Data Processing](#phase-1-data-processing)
- [Phase 2: Evaluating LLM Performance](#phase-2-evaluating-llm-performance)
- [Phase 3: Local Deployment and Automation](#phase-3-local-deployment-and-automation)
- [Phase 4: Cloud Deployment & Automation](#phase-4-cloud-deployment--automation)

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

## Phase 3: Local Deployment and Automation

### Deploy the RAG-based Q&A System Locally

- Develop a framework to automate textbook ingestion for new chapters.
- Host the system using local APIs or UI interfaces.
- Manage experiments and versions using MLflow.
- Use Docker for portability and reproducibility.

### Build a Local Textbook Agent

- Implement an agent-based system that can dynamically interact with textbook content.
- Explore LangChain Agents or custom retrieval strategies.

---

## Phase 4: Cloud Deployment & Automation

### Migrate the Local System to the Cloud

- Select a cloud provider: GCP, AWS, or Azure.
- Adapt code to use cloud-native services for storage, indexing, and model hosting.

### Automate the Workflow in the Cloud

- Set up Cloud Workflows to automate textbook processing, fine-tuning, and RAG deployment.
- Implement CI/CD pipelines for continuous integration and updates.
- Use serverless or container-based inference for scalable performance.

