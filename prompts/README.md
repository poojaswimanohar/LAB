## System Architecture: Online Quiz Maker using Google Colab

The system functions as an **end-to-end AI agent** for creating quizzes and automatically grading student answers using NLP models (GPT, BERT) in Google Colab.

             ┌─────────────────────┐
             │     Input (X)       │
             │  Quiz Data:         │
             │ - Questions         │
             │ - Answers           │
             │ - Student Responses │
             └─────────┬──────────┘
                       │
                       ▼
             ┌─────────────────────┐
             │ Quiz Creation Module │
             │ - Generate quizzes   │
             │ - Format questions   │
             │ - Set answer keys    │
             └─────────┬──────────┘
                       │
                       ▼
             ┌─────────────────────┐
             │ Student Interaction  │
             │ - Quiz delivery      │
             │ - Collect responses  │
             └─────────┬──────────┘
                       │
                       ▼
             ┌─────────────────────┐
             │ NLP Grading Engine   │
             │ - Compare answers    │
             │ - Use GPT/BERT to    │
             │   grade open-ended   │
             │   questions          │
             └─────────┬──────────┘
                       │
                       ▼
             ┌─────────────────────┐
             │ Feedback & Scoring   │
             │ - Assign grades      │
             │ - Provide hints/     │
             │   feedback           │
             └─────────┬──────────┘
                       │
                       ▼
             ┌─────────────────────┐
             │ Output (y)           │
             │ - Final Scores       │
             │ - Detailed Feedback  │
             │ - Analytics & Report │
             └─────────────────────┘


### Pipeline Components Explained:
- **Quiz Creation Module:** Generates quizzes based on input data, supports multiple question types (MCQs, short answers, essays).  
- **Student Interaction:** Delivers quizzes to students within Google Colab and collects their responses.  
- **NLP Grading Engine:** Uses LLMs (GPT, BERT) for evaluating open-ended answers, ensuring fairness and accuracy.  
- **Feedback & Scoring:** Computes scores, provides personalized feedback, and highlights areas for improvement.  

This architecture makes the system **fully automated**, scalable, and capable of **AI-powered grading**, while remaining user-friendly in a Colab environment.  

# Prompt Files for Online Quiz Maker AI Agent

This directory contains prompt examples for the **AI-powered Online Quiz Maker** implemented in Google Colab. The system supports both **quiz generation** and **automated grading** using NLP models (GPT, BERT).  

---

## 1. `simple_zero_shot_prompt.md`
**Type:** Zero-Shot Learning  
**Purpose:** Demonstrates single-instance quiz creation and grading without prior examples.  
**Use Case:** Quickly generate quizzes and grade student responses when no prior examples are available.  

### Key Features:
- Single quiz creation from input data  
- Automated grading for open-ended and MCQ questions  
- Standardized feedback and scoring format  
- Domain-specific terminology recognition  
- Quality metrics computation (accuracy, completeness, fairness)  

**Example Domain:** Undergraduate Computer Science course quiz  

[View `simple_zero_shot_prompt.md`](./simple_zero_shot_prompt.md)  

---

## 2. `few_shot_prompt.md`
**Type:** Few-Shot Learning  
**Purpose:** Demonstrates quiz generation and grading after learning from multiple (X, y) examples.  
**Use Case:** Improves grading accuracy and quiz quality when example quizzes are available.  

### Key Features:
- Three training examples from different educational domains:  
  1. Computer Science Fundamentals  
  2. Mathematics & Statistics  
  3. Business & Management  
- Pattern learning from diverse question formats and grading schemes  
- Application to new, unseen quiz inputs  
- Consistent formatting, scoring, and feedback standards  

**Training Examples Included:**  
- Intro to Programming Quiz (MCQs + Short Answers)  
- Probability & Statistics Quiz (MCQs + Numerical Problems)  
- Management Case Study Quiz (Open-Ended Essay Questions)  

**New Task:** AI-Powered Grading of Student Responses in Google Colab for a Machine Learning course  

[View `few_shot_prompt.md`](./few_shot_prompt.md)  

---

### Highlights:
- Supports **zero-shot and few-shot modes** for flexible AI interaction  
- Ensures **structured output**: quizzes, scores, and feedback in a standardized format  
- Integrates **GPT/BERT grading models** for reliable evaluation  
- Easy to extend with additional domains or question types  
- Fully compatible with **Google Colab** environment for education-focused deployments


