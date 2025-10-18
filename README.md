
# Neo4j Knowledge Graph AI

A practical implementation of AI-powered Knowledge Graph generation using Neo4j, Python, and OpenAI — transforming unstructured text into structured, queryable insights.

---

## Overview

This project demonstrates how Large Language Models (LLMs) and graph databases can work together to convert free-form text into a Knowledge Graph.  
It uses the Wikipedia API to collect domain text, applies OpenAI for entity extraction, and models relationships in Neo4j using Cypher queries.

The system highlights how graph-based representations support semantic reasoning, relationship discovery, and Retrieval-Augmented Generation (RAG) in modern AI pipelines.

---

## Key Features

- Entity Extraction: Uses OpenAI GPT to identify entities and their types from raw text.  
- Graph Construction: Automatically creates and merges nodes and relationships in Neo4j.  
- Cypher Query Language: Performs CRUD operations, filtering, and aggregations.  
- Visualization: Displays relationships among real-world AI entities such as OpenAI, Meta, DeepMind, and AGI.  
- Multi-Environment Support: Runs seamlessly in Neo4j Desktop, Sandbox, or Server editions.

---

## Architecture

```plaintext
Wikipedia Text
     │
     ▼
[ Entity Extraction ]
     │ (OpenAI GPT)
     ▼
[ Parsing & Normalization ]
     │
     ▼
[ Neo4j Graph Builder ]
     │ (Cypher MERGE)
     ▼
[ Knowledge Graph Visualization ]
````

---

## Technology Stack

| Category             | Tools / Libraries         |
| -------------------- | ------------------------- |
| Programming Language | Python 3.x                |
| Database             | Neo4j (Desktop / Sandbox) |
| AI Model             | OpenAI GPT-5-mini         |
| Data Source          | Wikipedia API             |
| Query Language       | Cypher                    |
| Environment          | Jupyter Notebook (macOS)  |

---

## Quick Start

### 1. Clone Repository

```bash
git clone https://github.com/venkateshreddy-code/neo4j-knowledge-graph-ai.git
cd neo4j-knowledge-graph-ai
```

### 2. Install Dependencies

```bash
pip install wikipedia-api neo4j openai==0.28
```

### 3. Configure Neo4j Connection

Edit the notebook to include your credentials:

```python
uri = "bolt://localhost:7687"
username = "neo4j"
password = "your_password"
```

### 4. Execute Notebook

Open the `.ipynb` file in Jupyter Lab or VS Code and run all cells sequentially to:

* Fetch text from Wikipedia
* Extract entities via OpenAI
* Generate graph structure in Neo4j
* Visualize results using Cypher

---

## Example Cypher Queries

```cypher
// Display all nodes and relationships
MATCH (n)-[r]->(m)
RETURN n, r, m;

// Explore specific entity relationships
MATCH (a:Organization {name:'OpenAI'})-[r]->(b)
RETURN a, r, b;

// Visualize schema
CALL db.schema.visualization();
```

---

## Example Output

```plaintext
(OpenAI) ── USES ──> (Artificial General Intelligence)
(Meta) ── RELATED_TO ──> (DeepMind)
(1956) ── INTRODUCED_IN ──> (AI Concept)
```

Displayed interactively in the Neo4j Browser for intuitive exploration.

---

## Learning Outcomes

* Practical understanding of graph databases and Cypher syntax
* Experience connecting LLMs to Neo4j for structured knowledge representation
* Insight into Knowledge Graphs for AI reasoning and RAG pipelines
* Hands-on implementation of entity-relationship modeling with modern AI tools

---

## Project Structure

| File                | Description                                                      |
| ------------------- | ---------------------------------------------------------------- |
| `neo4j_graph.ipynb` | Main notebook – entity extraction, graph creation, visualization |
| `README.md`         | Project documentation                                            |
| `.gitignore`        | Excludes cache, API keys, and system files                       |

---

## Future Enhancements

* Integration with Neo4j Graph Data Science (GDS) for clustering and link prediction
* Embedding LangChain or GraphRAG for contextual retrieval from the Knowledge Graph
* Streamlit-based dashboard for interactive exploration
* Additional data sources beyond Wikipedia (e.g., research papers, news)

---

## Author

**Venkatesh Reddy Ningam**
M.S. in Computer Science, Florida Atlantic University
[LinkedIn](https://www.linkedin.com/in/venkateshreddyningam/) | [GitHub](https://github.com/venkateshreddy-code)

---

If you found this project helpful, please consider starring the repository.


