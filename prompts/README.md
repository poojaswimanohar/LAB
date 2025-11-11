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
### Evaluation Metrics (From RAGAS Framework)

Both zero-shot and few-shot prompts support automated quality assessment of generated quizzes and AI-graded responses.

| Metric                     | Description                                                                 | Target |
|-----------------------------|-----------------------------------------------------------------------------|--------|
| **Faithfulness**            | Generated quizzes and grades are grounded in the source content (input material or syllabus). | ≥ 0.90 |
| **Answer Relevance**        | AI-graded responses align with expected answers or learning objectives.     | ≥ 0.90 |
| **Technical Term Coverage** | Domain-specific terminology is correctly recognized and applied in questions and answers. | ≥ 0.85 |
| **Compliance / Standards Score** | Generated content aligns with course or regulatory standards (curriculum, guidelines, HIPAA, etc.). | ≥ 0.95 |
| **Recall@k**                | Expected correct answers, key points, or learning objectives appear within the top-k AI outputs. | ≥ 0.80 |

This setup ensures the AI-generated quizzes and grading outputs are **accurate, consistent, and educationally reliable**.

---

### Domain-Specific Adaptations for Online Quiz Maker
### Domain-Specific Adaptations

The prompts can be adapted for various educational domains by modifying:

**Course Standards:**

- Computer Science: ACM CS Curriculum, IEEE Software Guidelines  
- Mathematics: Common Core, IB Math Standards  
- Biology / Science: AP Biology, IB Science Curriculum  

**Domain Terminology:**

- Computer Science: algorithm, variable, loop, function  
- Mathematics: equation, derivative, integral, matrix  
- Biology / Science: cell, DNA, enzyme, photosynthesis  

**Quiz / Answer Types:**

- Multiple Choice: standard MCQs with one or more correct answers  
- Short Answer: written answers graded by AI NLP models  
- Coding / Programming: code submissions graded using test cases and outputs  
- True/False / Fill-in-the-Blank: automatically checked by AI grading logic  

### Validation Checklist

Before considering output complete, verify:

- All quizzes and AI-graded responses follow a consistent and clear format.  
- Each question or graded response traces back to source material or student input.  
- Domain-specific terminology is correctly identified and applied.  
- Applicable course standards or guidelines are tagged.  
- No hallucinated content (all questions, answers, and feedback are grounded in input).  
- Ambiguous language is avoided (questions and feedback are clear and testable).  
- Completeness: all learning objectives and functional aspects are addressed.

### Key Technologies

- Large Language Models (GPT-4, BERT, T-5)  
- Retrieval-Augmented Generation (RAG)  
- RAGAS Evaluation Framework  
- Google Colab / Python for interactive quiz generation and grading



