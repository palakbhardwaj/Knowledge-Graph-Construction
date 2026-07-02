# 🧠 Knowledge Graph Construction 

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![spaCy](https://img.shields.io/badge/spaCy-NLP-09A3D5?style=for-the-badge)
![NetworkX](https://img.shields.io/badge/NetworkX-Knowledge%20Graph-FF6B35?style=for-the-badge)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-Dataset-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge)


</p>

<p align="center">
<b>Building an end-to-end Knowledge Graph from unstructured text using NLP, Named Entity Recognition, Relation Extraction, and NetworkX.</b>
</p>

---

# 🌟 Project Overview

Knowledge Graphs (KGs) represent information as interconnected entities and relationships, enabling semantic reasoning, explainable AI, GraphRAG, question answering, and intelligent search.

This project demonstrates a complete pipeline that transforms raw textual documents from the **20 Newsgroups Dataset** into a structured **Knowledge Graph**.

The workflow includes : 

- 📄 Text preprocessing
- 🧹 Data cleaning
- 🏷 Named Entity Recognition (NER)
- 🔗 Dependency-based relation extraction
- 📑 Subject–Relation–Object (SRO) triple generation
- 🕸 Knowledge Graph construction
- 📊 Graph analytics
- 📤 Graph export for Neo4j, Gephi, Cytoscape, and GraphRAG applications

---

# ✨ Key Features

- 📚 Built using the **20 Newsgroups Dataset**
- 🧹 Automatic text preprocessing
- 🏷 Named Entity Recognition using spaCy
- 🔗 Dependency-based Relation Extraction
- 📑 Subject–Relation–Object Triple Generation
- 🌐 Knowledge Graph Construction using NetworkX
- 📈 Graph Statistics and Network Analysis
- ⭐ PageRank Analysis
- 📊 Degree Centrality
- 🌍 Community Detection
- 🎨 Knowledge Graph Visualization

---

# 🏛 System Architecture

```text
                 20 Newsgroups Dataset
                          │
                          ▼
                 Dataset Loading
                          │
                          ▼
                  Text Cleaning
                          │
                          ▼
             Named Entity Recognition
                    (spaCy NER)
                          │
                          ▼
               Dependency Parsing
                          │
                          ▼
              Relation Extraction
                          │
                          ▼
         Subject ─ Relation ─ Object
                  Triple Creation
                          │
                          ▼
          Knowledge Graph Construction
             (NetworkX MultiDiGraph)
                          │
          ┌───────────────┴───────────────┐
          ▼                               ▼
   Graph Visualization            Graph Analytics
          │                               │
          └───────────────┬───────────────┘
                          ▼
              GraphML / GEXF Export
```

---

# 📂 Dataset

This project uses the **20 Newsgroups Dataset** provided by **scikit-learn**.

### Dataset Statistics

| Property | Value |
|-----------|-------|
| Documents | **11,314** |
| Categories | **20** |
| Dataset Type | Text Classification |
| Source | Scikit-learn |

Example categories include:

- comp.graphics
- sci.space
- sci.med
- rec.autos
- rec.sport.hockey
- rec.motorcycles
- talk.politics.misc
- talk.religion.misc
- misc.forsale

Dataset loading:

```python
from sklearn.datasets import fetch_20newsgroups

dataset = fetch_20newsgroups(
    subset="train",
    remove=("headers", "footers", "quotes")
)
```

---

# ⚙️ Technologies Used

| Technology | Purpose |
|------------|----------|
| Python | Programming Language |
| Pandas | Data Processing |
| NumPy | Numerical Computing |
| Scikit-learn | Dataset Loading |
| spaCy | NLP & Named Entity Recognition |
| NetworkX | Knowledge Graph Construction |
| Matplotlib | Graph Visualization |
| Regular Expressions | Text Cleaning |

---

# 📁 Repository Structure

```text
KnowledgeGraphProject
│
├── Knowledge Graph Project.ipynb
├── README.md
├── requirements.txt
│
├── outputs
│   ├── knowledge_graph.graphml
│   ├── knowledge_graph.gexf
│   ├── triples.csv
│   ├── entities.csv
│   ├── graph_statistics.csv
│   └── knowledge_graph.png
│
├── images
│   ├── pipeline.png
│   └── graph.png
│
└── notebooks
```

---

# 🔄 Complete Workflow

## Step 1 — Dataset Loading

Load the built-in **20 Newsgroups** dataset.

```python
fetch_20newsgroups()
```

---

## Step 2 — Text Preprocessing

Each document undergoes multiple preprocessing operations.

✔ Lowercase conversion

✔ URL removal

✔ Email removal

✔ Number removal

✔ Punctuation removal

✔ Extra whitespace removal

### Example

Before

```text
NASA launched the satellite in 2020!!
```

After

```text
nasa launched the satellite
```

---

## Step 3 — Named Entity Recognition (NER)

Named entities are extracted using **spaCy**.

Supported entity types include:

- PERSON
- ORG
- GPE
- LOC
- PRODUCT
- EVENT
- DATE
- NORP

Example:

| Entity | Type |
|---------|------|
| Apple | ORG |
| iPhone | PRODUCT |
| California | GPE |

---

## Step 4 — Relation Extraction

Dependency Parsing is used to identify semantic relationships.

Example:

Input Sentence

```text
Microsoft acquired GitHub.
```

Extracted Triple

```text
(Microsoft, acquired, GitHub)
```

---

## Step 5 — Triple Generation

Every sentence is transformed into

```text
(Subject,
 Relation,
 Object)
```

Example

```text
NASA launched Satellite
```

↓

```text
(NASA, launch, Satellite)
```

---

## Step 6 — Knowledge Graph Construction

The extracted triples are converted into a **NetworkX MultiDiGraph**.

### Nodes

Represent entities.

### Edges

Represent relationships.

Example

```text
NASA ───── launched ─────► Satellite

Microsoft ─ acquired ───► GitHub

Apple ───── created ────► MacBook
```

---

## Step 7 — Visualization

The graph is visualized using **NetworkX**.

Visualization includes:

- Node labels
- Directed edges
- Relationship labels
- Force-directed layout

---

## Step 8 — Graph Analytics

The following graph metrics are computed:

- Number of Nodes
- Number of Edges
- Density
- Average Degree
- Degree Distribution
- Degree Centrality
- Betweenness Centrality
- Closeness Centrality
- PageRank
- Connected Components
- Community Detection

---

## Step 9 — Graph Export

The final graph is exported in standard graph formats.

```
knowledge_graph.graphml
```

```
knowledge_graph.gexf
```

These files are compatible with:

- Neo4j
- Gephi
- Cytoscape
- yEd
- GraphXR

---

# 📊 Sample Knowledge Graph

```text
             Apple
               │
        manufactures
               │
               ▼
           MacBook

Microsoft ─ acquired ─► GitHub

NASA ───── launched ─► Satellite

Einstein ─ born_in ─► Germany
```

---

# 📑 Example Triples

| Subject | Relation | Object |
|----------|----------|--------|
| Microsoft | acquired | GitHub |
| Apple | manufactures | MacBook |
| NASA | launched | Satellite |
| Einstein | born_in | Germany |
| Google | developed | Android |

---

# 📤 Generated Outputs

Running the notebook produces:

```
✅ Named Entities

✅ Subject–Relation–Object Triples

✅ Knowledge Graph

✅ Graph Statistics

✅ PageRank Scores

✅ Degree Centrality

✅ Graph Visualization

✅ GraphML File

✅ GEXF File
```

---

# 🚀 Installation

Clone the repository

```bash
git clone https://github.com/yourusername/KnowledgeGraphProject.git
```

Move into the project

```bash
cd KnowledgeGraphProject
```

Install dependencies

```bash
pip install -r requirements.txt
```

Install the spaCy language model

```bash
python -m spacy download en_core_web_sm
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

or open directly in **Google Colab**.

---

# 📦 Requirements

```
Python >= 3.10

pandas

numpy

scikit-learn

spacy

networkx

matplotlib
```

---

# 📈 Applications

Knowledge Graphs have applications across numerous AI domains:

- 🔎 Semantic Search
- 🤖 GraphRAG
- 💬 Question Answering
- 🧠 Explainable AI
- 📚 Scientific Literature Mining
- 🏥 Healthcare Informatics
- 💰 Fraud Detection
- 🔐 Cybersecurity
- 🎯 Recommendation Systems
- 🌍 Search Engines
- 📊 Business Intelligence

---

# 🔮 Future Work

- Transformer-based Named Entity Recognition
- REBEL Relation Extraction
- Large Language Model Integration
- RDF Triple Store Support
- SPARQL Querying
- Neo4j Integration
- Graph Neural Networks (GNNs)
- Node2Vec Embeddings
- GraphRAG Pipeline
- Knowledge Graph Completion
- Link Prediction
- Temporal Knowledge Graphs
- Multimodal Knowledge Graphs

---

# 📚 References

1. Scikit-learn Documentation
2. spaCy Documentation
3. NetworkX Documentation
4. Neo4j Documentation
5. Google Knowledge Graph
6. RDF & OWL Specifications
7. GraphRAG Research Papers

---

# ⭐ If you found this project useful

Please consider giving this repository a ⭐ on GitHub.

It helps support the project and encourages future improvements.

---

<p align="center">
<b>Built with ❤️ using Python, spaCy, NetworkX, and NLP.</b>
</p>
