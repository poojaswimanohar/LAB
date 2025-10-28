**AI Quiz Creation & Grading AI Agent**

**End-to-End Prompting Examples**

**System Conceptualization**

**AI Agent Role:** Quiz Creation & Grading Processor (QCG-AI)

**Purpose:** An intelligent agent that can generate quizzes from study
material and grade student answers automatically with detailed feedback,
partial credit, and explanation of key reasoning.

**Processing Pipeline:**

-   **Input Reception →** Receive study material or student answer

-   **Data Understanding →** Parse text, identify key concepts

-   **Quiz/Answer Analysis →** Generate quiz questions or evaluate
    student answer

-   **Reasoning →** Detect ambiguities, calculate partial credit

-   **Explainability →** Highlight key phrases contributing to score

-   **Output Generation →** Produce graded answer or quiz in structured
    format

**PROMPT 1: Zero-Shot Example**

**User Input:**

You are QCG-AI, an expert AI Quiz Creation & Grading agent.

Your task is to process a student answer X and generate a structured
evaluation Y.

**INPUT (X):**

Question: Explain the difference between supervised and unsupervised
learning.

Student Answer: Supervised learning has labels. Unsupervised learning
finds hidden patterns in unlabeled data.

**TASK:**

Analyze this answer and provide:

-   Grade (0--10)

-   Partial Credit Explanation (if applicable)

-   Feedback Summary (clarity, completeness, correctness)

-   Explain key phrases influencing grading.

**AI Agent Output (Y):**

Grade: 9.5 / 10

Partial Credit Explanation: 0.5 points deducted for missing illustrative
examples.

**Feedback Summary:**

The student demonstrates a clear understanding of supervised and
unsupervised learning.

The distinction is accurate and mostly complete.

Adding an example for each would improve clarity.

Explainability (Key Phrases and Influence Scores):

\- \"Supervised learning has labels\" (0.95) -- core definition of
supervised learning

\- \"Unsupervised learning finds hidden patterns\" (0.92) -- core
definition of unsupervised learning

\- \"unlabeled data\" (0.88) -- key supporting detail

These influence scores (0--1) highlight which phrases contributed most
to the AI grading decision.

**Notes:**

-   Single-pass evaluation (no prior examples).

-   **Demonstrates** end-to-end AI reasoning and feedback generation

**PROMPT 2: Few-Shot Example**

**User Input:**

You are QCG-AI, an expert AI Quiz Creation & Grading agent.

Your task is to evaluate student answers using prior examples to ensure
consistent grading.

I will provide several example (X, Y) pairs, followed by a new student
answer to evaluate.

**EXAMPLE 1**

**INPUT (X₁):**

**Question: What is overfitting in machine learning?**

**Student Answer: When a model memorizes the training data and performs
poorly on new data.**

**OUTPUT (Y₁):**

Grade: 10/10

Feedback: Accurate and concise.

Partial Credit: N/A

Key Phrases: \"memorizes the training data\" (0.34), \"performs poorly
on new data\" (0.32)

**EXAMPLE 2**

**INPUT (X₂):**

Question: Define feature scaling.

Student Answer: Adjusting features to have similar ranges to improve
model convergence.

**OUTPUT (Y₂):**

Grade: 9/10

Feedback: Good explanation; could mention normalization/standardization
techniques.

Partial Credit: 1 point deducted for missing minor detail.

Key Phrases: \"similar ranges\" (0.31), \"model convergence\" (0.28)

**EXAMPLE 3**

**INPUT (X₃):**

Question: What is cross-validation?

Student Answer: A method for testing model performance using multiple
train-test splits.

**OUTPUT (Y₃):**

Grade: 9.5/10

Feedback: Strong answer; minor detail missing on K-fold validation.

Partial Credit: 0.5 points deducted

Key Phrases: \"multiple train-test splits\" (0.36), \"testing model
performance\" (0.29)

**NEW INPUT (X_new):**

Question: Explain supervised learning.

Student Answer: It uses labeled data to train models to predict outcomes
on new data.

**TASK**

Following the pattern in the examples, perform complete end-to-end
evaluation and generate output Y_new including:

-   Grade

-   Partial Credit (if applicable)

-   Feedback Summary

-   Key phrases with influence scores

**AI Agent Output (Y_new):**

Grade: 9.5 / 10

Partial Credit Explanation: 0.5 points deducted for missing illustrative
example.

**Feedback Summary:**

Clear and correct explanation of supervised learning.

Including an example would improve clarity.

Explainability (Key Phrases and Influence Scores):

\- \"labeled data\" (0.35) -- identifies core aspect of supervised
learning

\- \"train models\" (0.32) -- captures action performed

\- \"predict outcomes on new data\" (0.28) -- clarifies model purpose

These influence scores (0--1) highlight which phrases contributed most
to grading.
