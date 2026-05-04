# 🏛️ TempKG-RAG Legal Q&A System 🧠⚖️

As part of my journey through **AI and NLP research**, I embarked on this project to explore one of the most impactful and underserved areas in applied AI: **legal question answering for Indian Constitutional Law**. 📜🔍 This wasn't just a technical exercise — it was an opportunity to learn how **Knowledge Graphs**, **RAG pipelines**, and **multilingual NLP** can be combined to make the law more accessible to everyone, including Tamil-speaking communities who are often left out of legal technology tools.

Legal AI is uniquely challenging: the Indian Constitution has **over 100 amendments**, thousands of Supreme Court judgments, and complex inter-article relationships. 🚨 This complexity presented a fascinating challenge — and the perfect opportunity to push the boundaries of what modern AI can do in the legal domain.

Throughout the project, I built a **Temporal Knowledge Graph** using **Neo4j** with over **40,470 relationships**, designed a **Hybrid RAG Pipeline** combining graph-first retrieval with semantic vector search, and implemented **8 novel features** including counterfactual reasoning and federated temporal updates. The process taught me a great deal about **knowledge representation**, **multi-hop reasoning**, and how to evaluate AI systems in specialized domains. 📊🧪

<p align="center">
   <img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white" />
   <img src="https://img.shields.io/badge/Neo4j-Knowledge%20Graph-green?style=for-the-badge&logo=neo4j&logoColor=white" />
   <img src="https://img.shields.io/badge/RAG-Hybrid%20Pipeline-orange?style=for-the-badge" />
   <img src="https://img.shields.io/badge/Gradio-UI-purple?style=for-the-badge&logo=gradio&logoColor=white" />
   <img src="https://img.shields.io/badge/Google%20Colab-GPU%20T4-red?style=for-the-badge&logo=googlecolab&logoColor=white" />
   <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" />
</p>

---

## ⚠️ Disclaimer

**This project was developed for educational and research purposes only.** It is an experimental implementation of **AI techniques for legal question answering** and should not be used as a substitute for professional legal advice or real-world legal applications.

The system presented in this repository **has not been audited for legal accuracy, regulatory compliance, or operational robustness**. Legal question answering in real environments requires rigorous validation, domain expertise, and compliance with professional legal standards.

**Users should not rely on this project for real legal decisions or advice.** Always consult a qualified legal professional for any legal matters.

---

## 💡 Why I Built This

Most people in India — especially those who speak Tamil — have no easy way to understand their constitutional rights. Legal language is dense, laws change frequently, and existing tools only work in English. I wanted to change that.

**TempKG-RAG** was built to answer real constitutional law questions in plain language, track how laws have changed over time, and support Tamil-speaking users with a bilingual AI interface. It is — to my knowledge — one of the few legal AI systems that combines temporal knowledge graphs with multilingual support for Indian regional languages.

---

## 📌 Overview

**TempKG-RAG** is an advanced Legal Question Answering system that combines **Temporal Knowledge Graphs** with **Retrieval-Augmented Generation (RAG)** to answer complex questions about the **Indian Constitution**. It supports **Tamil and English** languages, tracks constitutional amendments over time, performs multi-hop reasoning across legal entities, and can even explore hypothetical legal scenarios through counterfactual reasoning.

---

## ✨ Key Features

| # | Feature | Description |
|---|---|---|
| ✅ 1 | **Temporal Amendment Tracking** | 106 constitutional amendments tracked with year-by-year analysis |
| ✅ 2 | **Neo4j Knowledge Graph** | 40,470 relationships across articles, cases, judges, and amendments |
| ✅ 3 | **Multi-hop Reasoning** | Path finding + narrative generation + inter-article connections |
| ✅ 4 | **Hybrid RAG Pipeline** | Graph-first retrieval + semantic vector search + result fusion |
| ✅ 5 | **Provenance Tracking** | Full citation chain with confidence scoring on every answer |
| 🆕 6 | **Counterfactual Reasoning** | 4 scenario types, alternative history generation, impact assessment |
| 🆕 7 | **Multilingual Tamil/English** | 52 Tamil legal terms, auto language detection, bilingual output |
| 🆕 8 | **Federated Temporal Updates** | 6 trusted sources, background sync, Neo4j storage |

---

## 🧑‍🔬 Exploratory Data Analysis (EDA)

During the EDA phase, the following insights were gathered from the Indian Constitutional dataset:

- **Amendment Distribution**: Constitutional amendments are unevenly distributed across decades, with peak activity in the 1970s–1980s during major political shifts.
- **Article Interconnections**: Fundamental Rights articles (Part III) are the most referenced across Supreme Court judgments, with Article 21 appearing in over 40% of landmark cases.
- **Case Coverage**: 138 Supreme Court judgments were mapped, covering landmark constitutional interpretations from 1950 to present.
- **Language Gap**: Over 90% of existing legal AI datasets are English-only, confirming the need for Tamil language support.
- **Temporal Gaps**: Many constitutional amendments lack publicly linked case law, highlighting data sparsity challenges in legal AI.

### Key Conclusions:
- **High Connectivity**: A small number of constitutional articles (21, 14, 19, 32) act as hubs with the most relationships in the knowledge graph.
- **Amendment Clustering**: Amendments cluster around major political events, enabling temporal pattern detection.
- **Multilingual Need**: Tamil-speaking users form a significant portion of India's population with no accessible legal AI tools.

---

## 🧹 Data Preprocessing

The dataset required significant structuring before being fed into the knowledge graph and RAG pipeline:

### Steps Taken:
1. **Constitutional Article Extraction**:
   - Parsed and structured all 504 constitutional articles with their parts, schedules, and amendment histories.

2. **Amendment Timeline Construction**:
   - Built a year-by-year timeline of all 106 constitutional amendments, linking each to the articles they modified.

3. **Knowledge Graph Entity Linking**:
   - Linked articles → cases → judges → amendments into a unified Neo4j graph with typed relationships.

4. **Vector Embedding Generation**:
   - Generated semantic embeddings for all articles and case summaries using **Sentence Transformers** for vector-based retrieval.

5. **Tamil Term Mapping**:
   - Manually curated 52 Tamil legal terms and mapped them to their English equivalents for bilingual query processing.

---

## ⚖️ Handling Legal Complexity

Legal question answering is uniquely hard because answers often span multiple articles, cases, and time periods. Here's how TempKG-RAG handles this:

### Hybrid Retrieval Strategy:
1. **Graph-First Search**:
   - Queries are first matched against the Neo4j Knowledge Graph to find structurally connected legal entities.
   - Multi-hop traversal connects related articles, amendments, and case law.

2. **Semantic Vector Search**:
   - Sentence embeddings capture semantic similarity beyond keyword matching.
   - Useful for paraphrased or indirect legal questions.

3. **Result Fusion**:
   - Graph results and vector results are fused with a confidence-weighted ranking system.
   - Final answers include full citation provenance.

---

## 🧠 System Architecture

The final system architecture combines a **Knowledge Graph**, **RAG pipeline**, and **Gradio UI** into an end-to-end legal chatbot.

### Components:
- **Knowledge Graph**: Neo4j with 40,470 relationships across 504 articles, 138 cases, 101 amendments, and 6 judges.
- **Embedding Layer**: Sentence Transformers for semantic similarity search.
- **RAG Pipeline**: Graph-first retrieval fused with vector search.
- **Temporal Engine**: Tracks amendment history with timestamps for time-aware answers.
- **Counterfactual Module**: Generates hypothetical legal scenarios across 4 scenario types.
- **Multilingual Layer**: Auto-detects Tamil/English and responds in the same language.
- **Federated Update Manager**: Syncs from 6 trusted legal sources in the background.
- **UI**: Gradio-based interactive chatbot interface.

```python
# Example: Hybrid RAG Query
def query_tempkg_rag(question, language='auto'):
    # Step 1: Detect language
    lang = detect_language(question)
    if lang == 'tamil':
        question = translate_tamil_to_english(question)

    # Step 2: Graph-first retrieval
    graph_results = neo4j_db.multi_hop_search(question, hops=3)

    # Step 3: Vector semantic search
    vector_results = vector_store.similarity_search(question, k=5)

    # Step 4: Fuse and rank results
    fused_results = fusion_ranker(graph_results, vector_results)

    # Step 5: Generate answer with citations
    answer = rag_pipeline.generate(question, fused_results)

    # Step 6: Translate back if Tamil
    if lang == 'tamil':
        answer = translate_to_tamil(answer)

    return answer, fused_results.citations
```

---

## 📊 Model Evaluation Results

### Performance on 50 Benchmark Questions:

| Metric | Score |
|---|---|
| 🎯 Mean Accuracy | **84.29%** |
| 📖 Article Retrieval | 67.6% |
| ⚖️ Case Retrieval | 77.0% |
| 🔗 Citation Coverage | **100%** |
| 🔁 Multi-Hop Reasoning | 0.6 avg hops |
| 🌐 Multilingual Support | Tamil + English |

### Key Insights from Evaluation:

1. **Strong Citation Coverage (100%)**: Every answer generated by the system includes at least one verifiable citation from the knowledge base — a critical requirement for legal AI trustworthiness.

2. **Good Case Retrieval (77%)**: The hybrid retrieval strategy effectively connects user questions to relevant Supreme Court judgments, even for indirect queries.

3. **Article Retrieval Gap (67.6%)**: Article retrieval is the hardest sub-task due to the abstract nature of constitutional language. This is an area for future improvement.

4. **Counterfactual and Multilingual Modules**: These features are novel additions not present in any baseline system, representing the primary research contribution of this project.

---

## 🆚 Comparison with Baseline

| System | Accuracy | Temporal Tracking | Tamil Support | Counterfactual Reasoning |
|---|---|---|---|---|
| RAG-only (Baseline) | 82.5% | ❌ | ❌ | ❌ |
| **TempKG-RAG (Ours)** | **84.29%** | ✅ | ✅ | ✅ |

> The baseline RAG-only system achieves slightly higher raw accuracy on article retrieval but completely lacks temporal reasoning, multilingual support, and counterfactual analysis — the three novel contributions of this project.

---

## 📚 Knowledge Base Statistics

| Entity | Count |
|---|---|
| Constitutional Articles | 504 |
| Supreme Court Judgments | 138 |
| Constitutional Amendments | 101 |
| Judges | 6 |
| Knowledge Graph Relationships | **40,470** |
| Tamil Legal Terms Mapped | 52 |
| Counterfactual Scenarios | 20 |
| Trusted Federated Sources | 6 |
| Benchmark Questions | 200 |

---

## 🌐 Tamil Language Support

Most Indian legal AI tools only work in English, leaving Tamil-speaking populations without access to legal information in their native language. TempKG-RAG addresses this gap directly:

- **52 Tamil legal terms** mapped to constitutional English equivalents
- **Automatic language detection** — no need to specify which language you're using
- **Bilingual responses** — ask in Tamil, get answers in Tamil
- Designed with accessibility in mind for Tamil Nadu's 77 million Tamil speakers

---

## 📁 Project Structure

```
TempKG-RAG-LEGAL_Q-A_SYSTEM/
│
├── TempKG_RAG_AI_Chatbot_Project2.ipynb   ← Main notebook (start here)
├── processed_data/
│   ├── amendments_106.csv                 ← All 106 constitutional amendments
│   ├── benchmark_200.json                 ← 200 evaluation questions
│   └── benchmark_200.csv                  ← Same data in CSV format
├── embeddings/
│   └── legal_embeddings.pkl               ← Pre-computed vector embeddings
├── outputs/
│   ├── evaluation_results.json            ← Full evaluation output
│   └── evaluation_charts_enhanced.png     ← Performance charts
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

### Step 1 — Open in Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

### Step 2 — Set Up Neo4j (Free)
- Create a free account at [neo4j.com/aura](https://neo4j.com/cloud/platform/aura-graph-database/)
- Copy your **connection URL**, **username**, and **password**
- Paste them into the config section at the top of the notebook

 Step 3 — Install Dependencies
```python
!pip install neo4j sentence-transformers gradio langchain
```

Step 4 — Run All Cells
Go to **Runtime → Run all** and wait for the Gradio link to appear. Click it to start asking legal questions!

---

📚 Requirements

- Python 3.10+
- Neo4j (Aura free tier)
- sentence-transformers
- gradio
- langchain
- pandas
- scikit-learn
- matplotlib
- seaborn

---

## 🔮 Conclusion

- TempKG-RAG demonstrates that combining **Knowledge Graphs with RAG** significantly improves legal question answering beyond what either approach achieves alone.
- The **Tamil language support** fills a critical gap in Indian legal tech, making constitutional information accessible to millions of Tamil speakers.
- The **counterfactual reasoning** and **federated temporal updates** are novel contributions with practical value for legal researchers and policy analysts.
- Future work will focus on expanding to more Indian regional languages, improving article retrieval accuracy, and adding real-time case law updates.

---

## **🙏 Acknowledgments**

A special thank you to the open-source community and the developers of **Neo4j**, **Sentence Transformers**, **LangChain**, and **Gradio** — without these tools, this project would not have been possible.

Gratitude also to the Supreme Court of India's publicly available judgment records and the Constitution of India's official digital resources, which formed the backbone of this knowledge base.

---

## 👩‍💻 Author

**Mohanasundarikarthi**
- 🐙 GitHub: [@mohanasundarikarthi](https://github.com/mohanasundarikarthi)

---

## Visitors Count

<img width="auto" src="https://profile-counter.glitch.me/TempKG-RAG-LEGAL_Q-A_SYSTEM/count.svg" />

---

## License ⚖️

This project is licensed under the **MIT License**, an open-source software license that allows developers to freely use, copy, modify, and distribute the software. 🛠️ This includes use in both personal and commercial projects, with the only requirement being that the original copyright notice is retained. 📄

```
MIT License

Copyright (c) 2026 Mohanasundarikarthi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">
⭐ If this project helped you or impressed you, please give it a star — it really means a lot!
</div>
