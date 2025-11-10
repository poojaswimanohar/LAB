# 🧠 Online Quiz Maker AI Agent

## 📘 Overview
This directory contains prompt examples for the **Online Quiz Maker using Google Colab** — an AI-powered system that generates quizzes, grades answers automatically, and provides instant feedback using Natural Language Processing (NLP) models like **GPT** and **BERT**.  
The system ensures scalability, fairness, and educational efficiency through adaptive question generation and AI-based grading.

---

## 🏗️ System Architecture Concept
The AI agent functions as an end-to-end quiz automation pipeline:

## System Architecture

```mermaid
graph TD;
    A["Input (X)"] --> B["AI Agent Pipeline"];
    B --> C["Data Understanding"];
    C --> D["Question Generation"];
    D --> E["Quiz Structuring & Formatting"];
    E --> F["Response Evaluation"];
    F --> G["AI Grading & Feedback Generation"];
    G --> H["Performance Summary & Analytics"];
    H --> I["Output (y)"];
**



System Input and Output

Input (X): Topic, syllabus, learning material, or student responses
Output (y): Generated quiz, graded answers, feedback, and performance summary
