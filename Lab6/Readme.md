# Lab 6 – Retrieval-Augmented Generation (RAG) Extension

**Student:** Mohini Naga Venkata Poojaswi Kankipati  
**Thesis Project:** Online Quiz Maker using Google Colab  
**Lab:** 1.6 – RAG Extension  

---

## 📝 Introduction

This lab extends the AI-powered quiz system developed in Lab 1.5 by integrating **Retrieval-Augmented Generation (RAG)** using a vector database.  
The system retrieves similar examples from a stored dataset to augment the prompt, improving the AI model's reasoning and output.

**Objectives:**

- Implement semantic search using a vector database (ChromaDB).  
- Retrieve the top 3 most relevant examples for a given input topic.  
- Generate AI quiz questions using augmented prompts via the Gemini API.  
- Demonstrate a full end-to-end AI workflow: Input → Retrieval → Generation → Output.

---

## ⚙️ System Workflow

1. **Input Topic:** User provides a topic (e.g., "Photosynthesis in plants").  
2. **Vector Retrieval:** System finds the 3 most similar (X, y) examples from ChromaDB.  
3. **RAG Prompt Construction:** Retrieved examples are combined with the topic to form an augmented prompt.  
4. **Quiz Generation:** Gemini API generates quiz questions using the augmented prompt.  
5. **Output Display:** Generated quiz is displayed along with retrieved examples.

---

## 🧰 Requirements

- Python 3.x  
- Google Colab  
- Libraries: `chromadb`, `sentence-transformers`, `google.generativeai`  
- Gemini API key stored securely in Colab secrets as `GEMINI_KEY`.

---

## 📂 Project Structure
/LAB
/Prompts
Zero_shot_prompt.md
Few_shot_prompt.md
/notebooks
/Lab6
Lab6.ipynb
README.md


---

## 🔗 Usage

1. Open the Colab notebook `Lab6_RAG_Notebook.ipynb`.  
2. Add your **Gemini API key** in Colab → Tools → Secrets → `GEMINI_KEY`.  
3. Run the notebook sequentially to:
    - Load prompts and dataset
    - Generate embeddings and store in ChromaDB
    - Retrieve top 3 examples for a topic
    - Generate quiz questions using Gemini API
    - Display retrieved examples and generated quiz

---

## ⚡ Results

- Retrieved examples provide contextually similar prior questions.  
- Quiz generation demonstrates the improvement in relevance using RAG.  
- End-to-end flow validates the AI agent pipeline: input → retrieval → reasoning → output.

---

## 🔍 Reflection

- **Benefits:** RAG improves output relevance by providing the model with contextually similar examples.  
- **Observations:** The system retrieves meaningful examples and generates quiz questions efficiently.  
- **Improvements:** Increase dataset size, diversify topics, and include automatic grading using few-shot prompts.  

---

## 📌 References

- [ChromaDB Documentation](https://docs.trychroma.com/)  
- [Google Generative AI API](https://developers.generativeai.google/)  
- Lab 1.5 – End-to-End AI Quiz System



