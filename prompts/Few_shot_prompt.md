## Prompt 2: Few-Shot Functional Requirements Extraction

### System Role
You are an expert **Educational AI Engineering** agent specialized in extracting **Functional Requirements (FRs)** for AI-based learning platforms.  
Your task is to analyze examples of quiz creation and AI grading workflows to generate well-structured, clear, and consistent functional requirements for the **Online Quiz Maker using Google Colab**.

---

### Learning Approach
This is a **few-shot learning** task.  
You will be provided with several (X, y) pairs showing example quiz and grading inputs along with their correctly extracted functional requirements.  
Use these examples to understand:

- **FR Structuring Patterns**  
- **Domain Terminology Recognition** (e.g., quiz generation, grading, feedback, NLP model, Google Colab)  
- **Compliance Mapping Strategies** (e.g., GDPR, Academic Integrity, Fair AI Use)  
- **Quality Validation Criteria**

Then, apply this learned pattern to extract functional requirements from a **new, unseen educational input** related to quiz creation, grading, or performance analytics.

## Training Examples for Few-Shot Learning

### Example 1: AI Grading Domain
**Input (X₁):**
<pre><code>
- **Document Type:** Change Request  
- **Domain:** Online Quiz Maker – AI Grading  
- **Compliance:** Academic Integrity, Fair AI Evaluation  
- **Content:**  
"We need to implement AI-based grading for short-answer questions.  
When a student submits an answer, the system should automatically evaluate correctness using GPT or BERT models.  
Grades should include a confidence score, and explanations must be generated for feedback.  
All grading actions should be logged for review by instructors." </code></pre>

**Output (y₁):**
<pre><code>
- **FR-101:** The system shall automatically grade student short-answer responses using AI models.  
  **Source:** "automatically evaluate correctness using GPT or BERT models"  
  **Domain Terms:** AI grading, short-answer evaluation, confidence score  
  **Compliance Tags:** Academic Integrity, Fair AI Evaluation  
  **Confidence Score:** 0.97

- **FR-102:** The system shall generate explanations for each graded response.  
  **Source:** "explanations must be generated for feedback"  
  **Domain Terms:** feedback, explanation generation, AI evaluation  
  **Compliance Tags:** Academic Transparency, Fair AI Evaluation  
  **Confidence Score:** 0.96  

- **FR-103:** The system shall log all grading actions for instructor review.  
  **Source:** "All grading actions should be logged for review by instructors"  
  **Domain Terms:** grading log, audit trail, instructor oversight  
  **Compliance Tags:** Academic Integrity, Audit Requirement  
  **Confidence Score:** 0.95</code></pre> 

---

### Example 2: Quiz Creation Domain
**Input (X₂):**
<pre><code>
- **Document Type:** User Story  
- **Domain:** Online Quiz Maker – Quiz Generation  
- **Compliance:** Academic Integrity, GDPR  
- **Content:**  
"As an instructor, I want to create multiple-choice quizzes from topic prompts.  
The system should generate questions automatically and allow importing questions via CSV.  
Students should be able to take quizzes in real-time, and their responses should be stored securely."</code></pre>

**Output (y₂):**
<pre><code>
- **FR-201:** The system shall automatically generate multiple-choice quiz questions from topic prompts.  
  **Source:** "generate questions automatically"  
  **Domain Terms:** quiz generation, multiple-choice, topic prompts  
  **Compliance Tags:** Academic Integrity, Fair AI Use  
  **Confidence Score:** 0.96  

- **FR-202:** The system shall allow quiz questions to be imported via CSV.  
  **Source:** "allow importing questions via CSV"  
  **Domain Terms:** CSV import, question bank, quiz creation  
  **Compliance Tags:** GDPR (data handling)  
  **Confidence Score:** 0.95  

- **FR-203:** The system shall store student responses securely and provide real-time access for grading.  
  **Source:** "responses should be stored securely"  
  **Domain Terms:** secure storage, real-time access, student responses  
  **Compliance Tags:** GDPR, Academic Integrity  
  **Confidence Score:** 0.97</code></pre>

---

### Example 3: Analytics and Feedback Domain
**Input (X₃):**
<pre><code>
- **Document Type:** SRS Excerpt  
- **Domain:** Online Quiz Maker – Performance Analytics  
- **Compliance:** Academic Integrity, GDPR  
- **Content:**  
"The system must track student performance for all quizzes.  
Analytics should include question-level accuracy, average scores, and response time.  
Instructors should be able to export performance data securely for reporting."</code></pre>

**Output (y₃):**
<pre><code>
- **FR-301:** The system shall track individual student performance on all quizzes.  
  **Source:** "track student performance for all quizzes"  
  **Domain Terms:** performance tracking, quiz analytics, student scores  
  **Compliance Tags:** Academic Integrity, GDPR  
  **Confidence Score:** 0.97  

- **FR-302:** The system shall provide analytics including question accuracy, average score, and response time.  
  **Source:** "Analytics should include question-level accuracy, average scores, and response time"  
  **Domain Terms:** analytics, question accuracy, response time  
  **Compliance Tags:** Academic Fairness  
  **Confidence Score:** 0.96  

- **FR-303:** The system shall allow instructors to securely export performance data.  
  **Source:** "Instructors should be able to export performance data securely"  
  **Domain Terms:** data export, secure reporting, instructor access  
  **Compliance Tags:** GDPR, Academic Integrity  
  **Confidence Score:** 0.95</code></pre>



---

## New Task: Apply Learned Pattern

Now that the AI agent has learned from previous few-shot examples, it should extract functional requirements from the following input:

**Input (X_new)**

- **Document Type:** Instructor Interview Notes  
- **Domain:** Online Quiz Maker – Automated Quiz Creation & AI Grading  
- **Compliance Standards:** GDPR, Academic Integrity, Fair AI Assessment  
- **Raw Content:**  

<pre><code>Interview with Dr. Emily Carter, Course Lead  
Date: November 12, 2025  

"Our platform should allow instructors to create quizzes quickly using topic prompts or uploaded question banks.  
The system must generate quizzes automatically, including multiple-choice and short-answer formats.  
Students should receive instant grading and detailed feedback with explanations.  
AI grading should include confidence scores for each evaluation.  
All quiz attempts, responses, and grades must be securely logged for instructor review.  
In case a quiz fails to generate or an answer cannot be graded, the instructor must receive an immediate alert.  
Analytics dashboards should summarize class performance, question-level accuracy, and completion rates.  
Data handling must comply with GDPR and maintain academic fairness."</code></pre>


---

### Expected Output (y_new)

The AI agent should produce structured functional requirements with:

- FR statements in the `FR-XXX` format  
- References to the source text for traceability  
- Key domain terms (e.g., quiz generation, AI grading, feedback, analytics)  
- Compliance and academic integrity tags  
- Confidence scores for each requirement  

---

### Guidance for AI Agent

Use prior examples to understand:

- The standard FR structure: "The system shall..."  
- Mapping source content to FRs  
- Recognition of domain-specific terminology  
- Tagging requirements with relevant compliance/academic standards  
- Assigning confidence scores that reflect certainty  

Apply this pattern to the input above.

---

### Functional Areas to Cover

- Automatic quiz generation from topic prompts or uploaded questions  
- AI grading for multiple-choice and short-answer questions  
- Instant feedback with explanations for students  
- Confidence scoring for AI-graded answers  
- Secure logging of student responses and grades  
- Instructor notifications for failures or errors  
- Analytics dashboards covering class performance and question accuracy  
- GDPR compliance and maintenance of academic integrity  

---

### Quality Metrics

Evaluate generated requirements using:

| Metric                     | Description                                        | Calculation Method |
|-----------------------------|--------------------------------------------------|------------------|
| **Faithfulness**            | Requirements grounded in source input           | Number of traceable claims / Total claims |
| **Answer Relevance**        | FRs align with stakeholder expectations          | Semantic similarity between FRs and input intent |
| **Technical Term Coverage** | Domain-specific terminology captured correctly   | Identified quiz/AI terms / Total domain terms |
| **Compliance Score**        | Adherence to regulatory and academic standards  | FRs with compliance tags / Total FRs |
| **Recall@k**                | Expected FRs present in generated output         | Expected requirements found / Total expected requirements |

**Target:** Extract 8–12 functional requirements covering all critical areas with average confidence ≥ 0.90

