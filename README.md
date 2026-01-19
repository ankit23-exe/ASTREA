
# 🌌 ASTREA

### A Space Biology Research Engine

**Winner (1st Place) — NASA International Space Apps Challenge 2025 (Ghaziabad Local Hackathon)** 🏆

ASTREA is an AI-powered research engine designed to help scientists and researchers explore large-scale space biology literature efficiently. It combines **semantic search**, **knowledge graph reasoning**, and **LLM-powered synthesis** to uncover hidden relationships across NASA bioscience studies.

Built by **Team Andromeda** during the NASA Space Apps Challenge 2025.

---

## 🚀 Problem Statement

NASA’s space biology research produces vast amounts of unstructured and semi-structured data—research papers, experimental reports, tables, and images.
However:

* Relevant insights are scattered across thousands of documents
* Cross-paper relationships are difficult to identify
* Traditional keyword search fails to capture semantic meaning

As a result, valuable connections remain hidden, slowing scientific discovery.

---

## 💡 Solution Overview

ASTREA introduces a **hybrid retrieval and reasoning system** that:

* Scrapes and ingests bioscience documents
* Extracts structured knowledge (entities & relationships)
* Stores information in **both**:

  * a **Vector Database** (semantic similarity)
  * a **Knowledge Graph** (explicit relationships)
* Answers user queries by **reasoning over both representations**

This allows ASTREA to go beyond simple document retrieval and generate **context-aware, insight-driven responses**.

---

## 🧠 System Architecture

### High-level flow:

1. **Document Ingestion**

   * Web scraping (HTML pages)
   * PDF document loading
2. **Chunking & Preprocessing**

   * Intelligent text chunking with overlap
   * Metadata enrichment (source, timestamp, type)
3. **Dual Storage Pipeline**

   * **Vector DB (Pinecone)**
     Stores embeddings for semantic retrieval
   * **Knowledge Graph (Neo4j)**
     Stores extracted entities and relationships as graph triples
4. **Query Processing**

   * User query is embedded and matched against vector DB
   * Related entities and edges fetched from Neo4j
5. **LLM Reasoning Layer**

   * Retrieved chunks + graph context are combined
   * LLM generates a grounded, reasoned response

> This hybrid approach enables both **semantic similarity** and **relational reasoning**.

---

## ✨ Key Features

* 🔍 **Semantic Search** across 600+ NASA bioscience studies
* 🧠 **Hybrid RAG Architecture** (Vector + Knowledge Graph)
* 🕸️ **Entity & Relationship Extraction** using LLMs
* 📊 **Neo4j Knowledge Graph** for relational exploration
* 📦 **Pinecone Vector Store** for scalable similarity search
* 🧩 **Intelligent Chunking** for high-quality retrieval
* 📄 **PDF + Web Content Support**
* 🚀 **Multiple Interfaces**: REST API, CLI, and programmatic usage

---

## 🛠️ Tech Stack

* **Backend**: Node.js, Express.js
* **Web Scraping**: Axios, Cheerio
* **LLMs & Embeddings**: OpenAI / Gemini (configurable)
* **Vector Database**: Pinecone
* **Knowledge Graph**: Neo4j
* **Document Processing**: Custom chunking pipeline
* **APIs**: RESTful endpoints

---

## 📦 Installation & Setup

### Prerequisites

Create a `.env` file in the root directory:

```env
GEMINI_API_KEY=your_api_key
OPENAI_API_KEY=your_api_key
PINECONE_INDEX_NAME=your_index_name
NEO4J_URI=your_neo4j_uri
NEO4J_USERNAME=your_username
NEO4J_PASSWORD=your_password
PORT=8080
```

### Install dependencies

```bash
npm install
```

---

## ▶️ Usage

### Start the server

```bash
npm start
# or
npm run dev
```

---

### REST API Endpoints

#### Scrape a single URL

```http
POST /scrape/url
```

```json
{
  "url": "https://example.com/research-paper"
}
```

#### Scrape multiple URLs

```http
POST /scrape/urls
```

```json
{
  "urls": ["https://site1.com", "https://site2.com"]
}
```

#### Ask a question

```http
POST /chat
```

```json
{
  "question": "How does microgravity affect gene expression in mice?"
}
```

---

### CLI Tool

```bash
npm run scraper-cli
```

The CLI supports:

* Single / multiple URL ingestion
* Progress tracking
* Error diagnostics

---

## 🧪 How ASTREA Thinks (Why It’s Different)

### Traditional RAG

```
Query → Retrieve Documents → LLM → Answer
```

### ASTREA’s Hybrid Reasoning

```
Query
  ↓
Vector Retrieval (Pinecone)
  +
Graph Traversal (Neo4j)
  ↓
Reasoning Layer
  ↓
LLM
  ↓
Insightful Answer
```

This allows ASTREA to:

* Infer relationships
* Connect experiments across papers
* Provide more grounded, explainable answers

---

## 🏆 Achievements

* 🥇 **Winner (1st Place)** — NASA International Space Apps Challenge 2025
  *Ghaziabad Local Hackathon*
* Built by **Team Andromeda**

**Team Members**:

* Anchita Jain
* Ankit Gupta
* Ashutosh Kumar Singh
* Ananya Patel
* Akhand Pratap Singh
* Lakshya Pratap Singh

---

## 🎥 Demo & Presentation

* 📽️ **Demo Video**:
  [https://drive.google.com/file/d/1sU4GM5Dd47xY-x1pKavkodyNyzcAPI7h/view](https://drive.google.com/file/d/1sU4GM5Dd47xY-x1pKavkodyNyzcAPI7h/view)
* 📄 **Pitch Deck & Architecture**: Included in repository

---

## 📜 License

This project is licensed under the **ISC License**.

---

## 🙌 Acknowledgements

Special thanks to:

* **NASA Space Apps Challenge**
* **Innogeeks & KIET Group of Institutions**
* Judges and mentors for valuable feedback and guidance


