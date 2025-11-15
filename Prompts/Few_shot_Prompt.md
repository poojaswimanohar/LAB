# Few-Shot Prompt Example: Online Quiz Maker

## Purpose
This prompt demonstrates how an AI agent can generate a 3-question multiple-choice quiz using a few-shot prompting approach. The AI is provided with several example input-output pairs (X → y) before generating a new quiz for a new topic.

---

## Task
You are an AI assistant for an online quiz system. Given a topic, generate a short 3-question multiple-choice quiz in JSON format, following the structure of provided examples.

- Each question must include:
  - Question text
  - 4 options labeled A-D
  - Correct answer

- Output format (JSON only, no extra text):

```json
[
  {
    "question": "string",
    "options": {"A": "string", "B": "string", "C": "string", "D": "string"},
    "answer": "A|B|C|D"
  }
]```


## Few-Shot Examples

### Example 1

**Topic:** "Data Structures Basics"

**Output:**

```json
[
  {"question": "Which data structure uses FIFO?", "options": {"A":"Stack","B":"Queue","C":"Linked List","D":"Tree"}, "answer":"B"},
  {"question": "Which data structure uses LIFO?", "options": {"A":"Stack","B":"Queue","C":"Linked List","D":"Graph"}, "answer":"A"},
  {"question": "Which data structure stores key-value pairs?", "options": {"A":"Array","B":"Dictionary","C":"Stack","D":"Queue"}, "answer":"B"}
]

**Example 2

Topic: "Python Basics"

Output:**

[
  {"question":"Which keyword is used for function definition?","options":{"A":"def","B":"func","C":"function","D":"define"},"answer":"A"},
  {"question":"Which symbol starts a comment?","options":{"A":"//","B":"#","C":"/*","D":"--"},"answer":"B"},
  {"question":"Which function prints output?","options":{"A":"echo","B":"print","C":"output","D":"write"},"answer":"B"}
]

**
New Topic for AI to Generate

Topic: "Supervised vs Unsupervised Machine Learning"

Expected Output:**

[
  {
    "question": "Which type of learning uses labeled data?",
    "options": {"A": "Supervised", "B": "Unsupervised", "C": "Reinforcement", "D": "Self-Supervised"},
    "answer": "A"
  },
  ...
]
