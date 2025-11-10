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

# How to Use These Prompts

## For Educators / Developers:

### 1. Choose the appropriate prompt type:
- **Use Zero-Shot** for quickly generating quizzes or grading student responses without prior examples.  
- **Use Few-Shot** for consistent quiz creation and grading when you have example quizzes or answers available.  

### 2. Customize the input section:
- Replace the sample **Quiz Content** with your actual questions or student responses.  
- Specify the **Course/Domain** (e.g., Computer Science, Mathematics, Business).  
- Set the **Question Type** (MCQ, Short Answer, Essay) as needed.  
- Optionally, provide previous examples for **Few-Shot** prompts to improve grading accuracy.  

### 3. Submit to an LLM:
- Use models like **GPT-4, BERT, or other fine-tuned models** integrated within Google Colab.  
- Ensure your input is properly formatted to maintain consistency in output.  

### 4. Evaluate the output using these metrics:
- **Faithfulness:** Are generated quizzes or grades grounded in the input content?  
- **Answer Relevance:** Do the graded responses align with expected answers?  
- **Technical Term Coverage:** Are domain-specific terms correctly handled?  
- **Scoring Accuracy:** Are the computed grades and feedback correct and fair?  

---

This workflow ensures that your AI agent can **automatically generate quizzes, grade student responses, and provide feedback** with high reliability and consistency in a Google Colab environment.

# Evaluation Metrics (Adapted from RAGAS Framework)

Both zero-shot and few-shot prompts support **automated quality assessment** of generated quizzes and AI-graded responses.

| Metric                     | Description                                           | Target |
|-----------------------------|-------------------------------------------------------|--------|
| **Faithfulness**            | Generated quizzes and grades are grounded in source content | ≥ 0.90 |
| **Answer Relevance**        | AI-graded responses align with expected answers or learning objectives | ≥ 0.90 |
| **Technical Term Coverage** | Domain-specific terminology is correctly recognized and applied | ≥ 0.85 |
| **Compliance / Standards Score** | Generated content aligns with course or regulatory standards | ≥ 0.95 |
| **Recall@k**                | Expected correct answers, key points, or learning objectives appear within the top-k AI outputs | ≥ 0.80 |

---

# Pseudocode Example: RAG-Style Quiz Generation and Grading
<pre><code>
def generate_quiz_and_grade(student_input, course_domain, examples=None):
    """
    RAG-style pipeline for quiz creation and AI grading.
    """
    # 1. Preprocess input
    cleaned_input = preprocess(student_input)

    # 2. Retrieve relevant context from knowledge base
    context = rag_retrieval(cleaned_input, course_domain)

    # 3. Construct prompt with context
    if examples:
        prompt = construct_few_shot_prompt(cleaned_input, context, examples)
    else:
        prompt = construct_zero_shot_prompt(cleaned_input, context)

    # 4. Generate quizzes or grades via LLM
    output = llm.generate(prompt)

    # 5. Validate and structure output
    validated_output = validate_quiz_and_grades(output, course_domain)

    return validated_output
  </code></pre>
# Online Quiz Maker – System Architecture

The AI agent for **Online Quiz Maker** functions as an end-to-end solution for **quiz creation and automated grading**.

| Step | Component | Description |
|------|-----------|-------------|
| 1 | **Input (X)** | Raw quiz content, student answers, or course material provided by the user. |
| 2 | **Document Preprocessing** | Cleans, normalizes, and segments input for downstream processing. |
| 3 | **Knowledge Base Construction** | Organizes processed content into a searchable knowledge repository for context retrieval. |
| 4 | **Contextual Retrieval (RAG)** | Fetches relevant context from the knowledge base to guide the LLM for quiz generation and grading. |
| 5 | **LLM Processing & Generation** | Uses LLMs (e.g., GPT, BERT) to create quizzes, grade answers, and provide feedback. |
| 6 | **Quality Validation** | Ensures generated quizzes and grades are accurate, complete, consistent, and aligned with course standards. |
| 7 | **Output (y)** | Structured quizzes, grades, and feedback ready for review or delivery to students. |

**Workflow Overview:**  



