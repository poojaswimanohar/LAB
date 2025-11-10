# 🎓 Online Quiz Maker AI Agent – Lab 1.4 Prompts

## Overview
This directory contains prompt examples for the **Automated Quiz Generation and Grading System** using Google Colab and Large Language Models (LLMs).  
The system allows educators to automatically generate quizzes, grade both objective and descriptive answers, and provide instant feedback.

The AI agent is conceptualized as an **end-to-end solution**:

```mermaid
graph TD
    A[Input (X)] --> B[AI Agent Pipeline]
    B --> C[Data Understanding]
    C --> D[Question Generation]
    D --> E[Quiz Structuring & Formatting]
    E --> F[Response Evaluation (Objective & Subjective)]
    F --> G[AI Grading & Feedback Generation]
    G --> H[Performance Summary & Analytics]
    H --> I[Output (y)]



**Input (X):** Topic, syllabus, learning material, or student responses  
**Output (y):** Generated quiz, graded answers, feedback, and performance summary  

---

## Prompt Files

### 1. `simple_zero_shot_prompt.md`
- **Type:** Zero-Shot Learning  
- **Purpose:** Generate quizzes and grade answers without prior examples  
- **Use Case:** Quick one-off quiz creation and grading  

**Key Features:**
- Single-topic quiz generation  
- Automatic question type classification (MCQ, short answer, descriptive)  
- Instant grading and feedback  
- Output includes score, explanation, and confidence metrics  

**Example Domain:**  
Undergraduate Computer Science – “Python Basics”

---

### 2. `few_shot_prompt.md`
- **Type:** Few-Shot Learning  
- **Purpose:** Generate and grade quizzes using prior examples  
- **Use Case:** Improved accuracy and consistency when example quizzes are available  

**Key Features:**
- Uses 3 training examples from education topics (Python, Algebra, English)  
- Learns question and answer patterns from examples  
- Grades descriptive answers consistently  
- Generates feedback and performance summaries  

**Training Examples Included:**
1. Python Programming Quiz – auto-graded using GPT similarity scoring  
2. Algebra Problem Set – evaluated for formula correctness  
3. Reading Comprehension Exercise – graded with BERT-based textual similarity  

**New Task:** Generate a quiz and evaluate answers for “Loops in Python.”

---

## How to Use These Prompts

1. Choose the prompt type:  
   - **Zero-Shot:** new topic, no prior examples  
   - **Few-Shot:** topic with prior examples  

2. Replace placeholders under **Input (X)** with your topic, number of questions, difficulty, or student answers.  

3. Run the prompt in Google Colab with an LLM (e.g., GPT-4 or BERT).  

4. Review the output: generated quiz, graded answers, and feedback.  

---
Question ID: Q-001
Question: What is the output of print(2 ** 3)?
Options: [A] 5, [B] 6, [C] 8, [D] 9
Correct Answer: [C]
Difficulty: Easy
Student Answer: "8"
Score: 1.0
Feedback: Correct! You understood the concept of exponentiation.
Confidence Score: 0.97

---

## Notes
- All prompts demonstrate **end-to-end AI agent functionality** (input → pipeline → output).  
- Zero-shot prompts generate quizzes without prior examples.  
- Few-shot prompts use example quizzes and grading to improve performance and consistency.  
- Outputs are fully structured, testable, and include feedback.  
- Designed for educational use, adaptable across multiple subjects and difficulty levels.

## Expected Output Format

