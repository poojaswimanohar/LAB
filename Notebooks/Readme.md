# Lab 5 – Online Quiz Maker (End-to-End AI System)

## Project Overview
This lab demonstrates a fully operational AI-powered quiz system implemented in **Google Colab** using the **Gemini API**. It extends the conceptual work from Lab 1.4, where prompt-engineered AI agents were designed. The system can:

1. Generate quizzes on a given topic (zero-shot prompts)
2. Grade student answers (few-shot prompts)
3. Demonstrate an end-to-end workflow

The notebook integrates real API calls using the Gemini key stored securely in Colab Secrets.

---

## Notebook

**Colab Notebook:** [OnlineQuizMaker.ipynb](Notebooks/OnlineQuizMaker.ipynb)

**Contents:**
1. **Step 1:** Load Gemini API key securely from Colab Secrets
2. **Step 2:** Load zero-shot and few-shot prompts from GitHub
3. **Step 3:** Generate quiz questions via Gemini API
4. **Step 4:** Grade student answers via Gemini API
5. **Step 5:** End-to-end demonstration (topic → quiz → grading → display)
6. **Step 6:** Reflection on system design and improvements

---

## Setup Instructions

1. Add your **Gemini API key** in Colab Secrets:
   - Go to `Tools → Secrets → Create new secret`
   - Name: `GEMINI_KEY`
   - Value: `<your Gemini API key>`
2. Run the notebook cells in order. Make sure `zero-shot` and `few-shot` prompt files are present in the GitHub `Prompts/` directory.

---

## Reflection

- The system automatically generates quizzes and grades answers using AI.
- Zero-shot prompts are used for quiz creation; few-shot prompts for grading.
- Real Gemini API calls ensure accurate output.
- Improvements could include multiple topics, multiple-choice questions, and handling larger student answer sets.
