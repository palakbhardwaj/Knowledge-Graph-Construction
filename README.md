# 🧠 Knowledge Graph Construction from the 20 Newsgroups Dataset

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue.svg">
  <img src="https://img.shields.io/badge/scikit--learn-Dataset-orange.svg">
  <img src="https://img.shields.io/badge/spaCy-NLP-green.svg">
  <img src="https://img.shields.io/badge/NetworkX-Knowledge%20Graph-red.svg">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg">
</p>

---

# 📌 Overview

This project demonstrates the complete pipeline for constructing a **Knowledge Graph (KG)** from raw textual data using **Natural Language Processing (NLP)** techniques.

The project utilizes the **20 Newsgroups** dataset from **scikit-learn**, performs text preprocessing, extracts named entities and semantic relationships using **spaCy**, converts them into **Subject–Relation–Object (SRO)** triples, and constructs a directed knowledge graph using **NetworkX**.

The generated graph can be visualized, analyzed, and exported into standard graph formats such as **GraphML** and **GEXF** for further exploration in **Neo4j**, **Gephi**, or **Cytoscape**.

---

# 🚀 Features

- ✅ Uses built-in 20 Newsgroups dataset
- ✅ Automatic text preprocessing
- ✅ Named Entity Recognition (NER)
- ✅ Dependency-based Relation Extraction
- ✅ Subject–Relation–Object Triple Generation
- ✅ Knowledge Graph Construction
- ✅ Interactive Graph Visualization
- ✅ Graph Statistics
- ✅ PageRank Analysis
- ✅ Degree Centrality
- ✅ Community Detection
- ✅ GraphML Export
- ✅ GEXF Export
- ✅ Ready for Neo4j and GraphRAG

---

# 📂 Dataset

The project uses the **20 Newsgroups Dataset** available directly from **scikit-learn**.

It contains approximately

- **11,314 training documents**
- **20 different categories**

Examples include:

- comp.graphics
- sci.space
- rec.autos
- rec.sport.hockey
- talk.politics.misc
- misc.forsale

No manual download is required.

```python
from sklearn.datasets import fetch_20newsgroups

dataset = fetch_20newsgroups(
    subset="train",
    remove=("headers","footers","quotes")
)
```

---

# 🏗️ Project Pipeline

```text
20 Newsgroups Dataset
            │
            ▼
Load Dataset
            │
            ▼
Text Cleaning
            │
            ▼
Named Entity Recognition (spaCy)
            │
            ▼
Relation Extraction
            │
            ▼
Subject–Relation–Object Triples
            │
            ▼
Knowledge Graph Construction
            │
            ▼
Graph Visualization
            │
            ▼
Graph Analysis
            │
            ▼
GraphML / GEXF Export
```

---

# ⚙️ Technologies Used

| Technology | Purpose |
|------------|----------|
| Python | Programming |
| Pandas | Data Processing |
| Scikit-learn | Dataset |
| spaCy | Named Entity Recognition |
| NetworkX | Knowledge Graph Construction |
| Matplotlib | Visualization |
| Regex | Text Cleaning |

---

# 📁 Project Structure

```text
KnowledgeGraphProject/

│
├── Knowledge Graph Project.ipynb
├── README.md
├── requirements.txt
│
├── outputs/
│     ├── knowledge_graph.graphml
│     ├── knowledge_graph.gexf
│     ├── triples.csv
│     ├── entities.csv
│     └── graph.png
│
└── images/
```

---

# 📖 Workflow

## 1️⃣ Dataset Loading

The project automatically loads the built-in **20 Newsgroups** dataset.

```python
fetch_20newsgroups()
```

---

## 2️⃣ Text Preprocessing

The following preprocessing steps are performed:

- Lowercase conversion
- URL removal
- Email removal
- Number removal
- Punctuation removal
- Extra whitespace removal

Example

Before

```
NASA launched the satellite in 2020!!
```

After

```
nasa launched the satellite in
```

---

## 3️⃣ Named Entity Recognition (NER)

Entities are extracted using **spaCy**.

Detected entity types include:

- PERSON
- ORG
- GPE
- LOC
- DATE
- PRODUCT
- EVENT

Example

Input

```
Apple released the new iPhone in California.
```

Output

| Entity | Label |
|---------|-------|
| Apple | ORG |
| iPhone | PRODUCT |
| California | GPE |

---

## 4️⃣ Relation Extraction

Relationships between entities are extracted using **Dependency Parsing**.

Example

Sentence

```
Microsoft acquired GitHub.
```

Extracted Triple

```
(Microsoft, acquired, GitHub)
```

---

## 5️⃣ Triple Generation

Each sentence is converted into

```
(Subject,
 Relation,
 Object)
```

Example

```
NASA

launched

Satellite
```

becomes

```
(NASA, launch, Satellite)
```

---

## 6️⃣ Knowledge Graph Construction

The graph is built using **NetworkX MultiDiGraph**.

Each

Entity → Node

Each

Relationship → Edge

Example

```
Apple -------- manufactures --------► MacBook

NASA -------- launched ------------► Satellite

Einstein ---- born_in ------------► Germany
```

---

## 7️⃣ Visualization

The generated graph is visualized using **NetworkX** and **Matplotlib**.

The graph includes:

- Node labels
- Directed edges
- Relationship labels

---

## 8️⃣ Graph Analysis

The project computes several graph statistics:

- Number of Nodes
- Number of Edges
- Degree Distribution
- Degree Centrality
- PageRank
- Connected Components

---

## 9️⃣ Graph Export

The final graph is exported as

```
knowledge_graph.graphml
```

and

```
knowledge_graph.gexf
```

These files can be opened directly in

- Neo4j
- Gephi
- Cytoscape
- yEd

---

# 📊 Example Triple

| Subject | Relation | Object |
|----------|----------|--------|
| Microsoft | acquired | GitHub |
| Apple | manufactures | MacBook |
| NASA | launched | Satellite |
| Einstein | born_in | Germany |

---

# 📈 Sample Graph

```
NASA -------- launch --------► Satellite

Apple ------- make ----------► Computer

Microsoft --- acquire ------► GitHub

Einstein ---- born_in ------► Germany
```

---

# 📤 Outputs

The project generates

- Knowledge Graph
- Triple Dataset
- Entity Dataset
- GraphML File
- GEXF File
- Graph Visualization
- Graph Statistics

---

# 💻 Installation

Clone the repository

```bash
git clone https://github.com/yourusername/KnowledgeGraphProject.git

cd KnowledgeGraphProject
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook

```bash
jupyter notebook
```

or open directly in **Google Colab**.

---

# 📦 Requirements

```
pandas
scikit-learn
spacy
networkx
matplotlib
```

Install spaCy model

```bash
python -m spacy download en_core_web_sm
```

---

# 📌 Applications

Knowledge Graphs are widely used in

- Search Engines
- Recommendation Systems
- Healthcare
- Cybersecurity
- Scientific Literature Mining
- Semantic Search
- Explainable AI
- GraphRAG
- Question Answering
- Fraud Detection

---

# 🔮 Future Improvements

- Transformer-based NER
- REBEL Relation Extraction
- Neo4j Integration
- RDF Triple Store
- Graph Neural Networks (GNNs)
- Node2Vec Embeddings
- Knowledge Graph Completion
- GraphRAG
- Question Answering over Knowledge Graphs
- Temporal Knowledge Graphs
- Multimodal Knowledge Graphs

---

# 📚 References

- Scikit-learn 20 Newsgroups Dataset
- spaCy Documentation
- NetworkX Documentation
- Neo4j Documentation
- Google Knowledge Graph
- RDF & OWL Specifications

---
