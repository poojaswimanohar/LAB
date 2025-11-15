# Zero-Shot Prompt Example: Online Quiz Maker

## Purpose
This prompt demonstrates an AI agent generating a 3-question multiple-choice quiz based on a given topic. It also shows the expected output format for grading student answers.

---

You are an AI assistant for an online quiz system.

### Task 1: Quiz Generation
Given a topic, generate a short 3-question multiple-choice quiz. Each question should include:
- Question text
- 4 options labeled A-D
- Correct answer

**Topic (X):** "Supervised vs Unsupervised Machine Learning"

**Output format (y) as JSON array only, no extra text:**

```json
[
  {
    "question": "string",
    "options": {"A": "string", "B": "string", "C": "string", "D": "string"},
    "answer": "A|B|C|D"
  }
]

**Expected Example Output:**
[
  {
    "question": "Which type of learning uses labeled data?",
    "options": {"A": "Supervised", "B": "Unsupervised", "C": "Reinforcement", "D": "Self-Supervised"},
    "answer": "A"
  },
  {
    "question": "Which type of learning finds patterns in unlabeled data?",
    "options": {"A": "Supervised", "B": "Unsupervised", "C": "Reinforcement", "D": "Semi-Supervised"},
    "answer": "B"
  },
  {
    "question": "Which method requires input and output data?",
    "options": {"A": "Supervised", "B": "Unsupervised", "C": "Reinforcement", "D": "Self-Supervised"},
    "answer": "A"
  }
]
