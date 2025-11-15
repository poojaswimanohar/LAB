# Online Quiz Maker using AI – Lab 5

**Author:** Mohini Naga Venkata Poojaswi Kankipati  
**Thesis:** Online Quiz Maker using AI-powered prompt engineering  

## Description
This repository contains the Lab 5 implementation of an AI-powered Online Quiz Maker.  
The system demonstrates an **end-to-end AI pipeline** for creating quizzes and grading student answers using prompt engineering (zero-shot and few-shot prompts).  

Due to API limitations, the notebook currently uses **simulated outputs** to demonstrate quiz generation and grading. The pipeline is fully functional and ready for integration with the Gemini API or other AI models.

## Repository Structure


## How to Run
1. Open the notebook `Lab5_Online_Quiz_Maker.ipynb` in Google Colab.  
2. Ensure the `/Prompts/` folder exists with the prompt files.  
3. (Optional) Set your Gemini API key in Colab secrets (`GEMINI_KEY`) if using real API calls.  
4. Run all cells to see the end-to-end workflow:  
   - Topic input → Quiz generation → Student answers → Grading → Output display.  

## Reflection
- The system generates quizzes and grades answers automatically.  
- Zero-shot prompts are used for quiz creation; few-shot prompts are used for grading.  
- The end-to-end workflow demonstrates **input → reasoning → output** clearly.  
- Future improvements could include multiple topics, multiple-choice questions, GUI integration, and real Gemini API usage.  

## License
This project is for academic purposes and does not have a commercial license.
