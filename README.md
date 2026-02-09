## 📘Transformer-Based Anime Recommendation System

### 🔍 Problem Statement
With a large number of anime titles available, users face difficulty discovering content that aligns with their interests. Keyword-based or popularity-driven recommendations often fail to capture deeper semantic meaning. This project addresses the problem by building a **semantic, content-based recommendation system using Transformer models** to generate high-quality anime recommendations.

---

### 🧠 Core Approach
This project uses a **Transformer-based NLP approach** to generate **dense semantic embeddings** for anime descriptions and genres. Instead of relying on traditional keyword matching, the system captures **contextual meaning** using pre-trained transformer models and recommends anime based on semantic similarity.

---

### 📊 Data Understanding
- Dataset loaded from `anime.csv`
- Key fields used:
  - Anime title
  - Genre
  - Synopsis / description
- Relevant text columns were merged into a single textual feature to enrich semantic context
- Missing values and inconsistent text formats were handled before modeling

---

### 🧹 Text Preprocessing
Although transformer models require minimal preprocessing, the following steps were applied to improve input quality:
- Lowercasing text
- Removing null and duplicate entries
- Basic text normalization (special character cleanup)
- Concatenation of genre and synopsis to improve contextual signals

Heavy preprocessing (stemming/lemmatization) was intentionally avoided to preserve semantic meaning for transformers.

---

### 🤖 Transformer-Based Feature Extraction
- Used **pre-trained Transformer models** (Sentence Transformers)
- Converted each anime’s combined text into **dense vector embeddings**
- Captured contextual and semantic relationships between anime titles
- Generated high-dimensional embedding representations for all anime entries

Transformer embeddings enable understanding of synonyms, themes, and narrative similarity beyond keyword overlap.

---

### 🔢 Libraries & Models Used
- **pandas** – dataset handling  
- **numpy** – numerical operations  
- **sentence-transformers** – transformer-based text embeddings  
- **transformers** – pre-trained NLP models  
- **sklearn.metrics.pairwise** – cosine similarity computation  

---

### 📐 Similarity Computation
- Applied **cosine similarity** on transformer-generated embeddings
- Built a similarity matrix representing semantic closeness between anime
- Higher similarity scores indicate stronger narrative and thematic similarity

Cosine similarity is well-suited for dense embedding spaces produced by transformers.

---

### 🎯 Recommendation Pipeline
1. User inputs an anime title  
2. System retrieves the corresponding embedding  
3. Cosine similarity is computed against all other anime embeddings  
4. Anime are ranked by similarity score  
5. Top N most semantically similar anime are returned  

This pipeline ensures **context-aware, explainable recommendations**.

---

This qualitative evaluation is appropriate for transformer-based content systems.

---

### 🚀 Future Enhancements
- Add user interaction data for hybrid recommendations
- Fine-tune transformer models on anime-specific text
- Deploy as a Streamlit web application
- Store embeddings using vector databases (FAISS / Pinecone)

---

### 💡 Key Learnings
- Practical application of transformer-based NLP models
- Working with semantic embeddings and vector similarity
- Designing scalable, explainable recommendation systems
- Understanding trade-offs between traditional NLP and transformers
