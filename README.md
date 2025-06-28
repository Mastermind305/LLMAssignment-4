# LLMAssignment-4
Sentiment Analysis and Prompt Engineering with TinyLlama
This repository contains two Jupyter notebooks (assign4.1.ipynb and assignmen4.2.ipynb) that demonstrate the use of the TinyLlama/TinyLlama-1.1B-Chat-v1.0 model from Hugging Face for natural language processing tasks, specifically focusing on prompt engineering and sentiment analysis. The notebooks explore different prompting techniques to generate text and evaluate their effectiveness.
Table of Contents

Overview
Files
Setup Instructions
Notebook Descriptions
assign4.1.ipynb
assignmen4.2.ipynb


Dependencies
Usage
Results
Contributing
License

Overview
The project showcases the application of the TinyLlama model for text generation tasks. The notebooks compare different prompting strategies (direct, few-shot, and chain-of-thought) for explaining concepts and classifying sentiments. Additionally, assign4.1.ipynb includes semantic similarity analysis using the sentence-transformers library to evaluate the quality of generated outputs.
Files

assign4.1.ipynb: Explores prompt engineering for explaining the concept of photosynthesis using direct, few-shot, and chain-of-thought (CoT) prompts. It also evaluates the generated outputs using cosine similarity scores.
assignmen4.2.ipynb: Focuses on sentiment analysis of text inputs using basic, instruction-based, and few-shot prompting techniques.

Setup Instructions
To run the notebooks, follow these steps:




Set Up a Virtual Environment:
python -m venv flas1
source flas1/bin/activate  # On Windows: flas1\Scripts\activate


Install Dependencies:Install the required Python packages using the following command:
pip install transformers accelerate sentencepiece sentence-transformers torch numpy


Run Jupyter Notebook:Launch Jupyter Notebook and open the desired .ipynb file:
jupyter notebook



Notebook Descriptions
assign4.1.ipynb
This notebook demonstrates the use of different prompting techniques to explain the concept of photosynthesis:

Direct Prompt: A simple query asking for an explanation of photosynthesis.
Few-Shot Prompt: Provides examples of question-answer pairs before asking for the photosynthesis explanation.
Chain-of-Thought (CoT) Prompt: Breaks down the explanation into steps before summarizing.

The notebook also uses the sentence-transformers model (all-MiniLM-L6-v2) to compute cosine similarity scores between generated outputs and a reference answer to evaluate their semantic similarity.
Key Outputs:

Direct Prompt: Generates a list of related questions rather than a direct explanation.
Few-Shot Prompt: Provides a concise but slightly inaccurate explanation.
CoT Prompt: Offers a detailed and accurate summary, with the highest cosine similarity score (0.8881) to the reference answer.

assignmen4.2.ipynb
This notebook focuses on sentiment analysis of three sample texts using the TinyLlama model with different prompting strategies:

Basic Prompt: Directly asks for the sentiment of the text.
Instruction Prompt: Explicitly instructs the model to classify sentiment as Positive, Negative, or Neutral.
Few-Shot Prompt: Provides example texts with labeled sentiments before classifying the target text.

Sample Texts:

"I absolutely love this movie! It was fantastic and inspiring."
"The product was okay, but it could be better."
"I hate this restaurant. The food was awful and the service terrible."

Key Outputs:

The few-shot prompt generally provides the most consistent and accurate sentiment classifications (Positive, Neutral, Negative).
The basic and instruction prompts occasionally produce inconsistent or overly verbose outputs.

Dependencies

Python 3.9.20
transformers==4.53.0
accelerate==1.8.1
sentencepiece==0.2.0
sentence-transformers==4.1.0
torch==2.5.1
numpy==2.0.2

Usage

Open either assign4.1.ipynb or assignmen4.2.ipynb in Jupyter Notebook.
Ensure the flas1 virtual environment is activated and all dependencies are installed.
Run the cells sequentially to load the model, generate outputs, and (for assign4.1.ipynb) compute similarity scores.
Review the printed outputs to compare the effectiveness of different prompting strategies.

Results

assign4.1.ipynb: The CoT prompt produces the most accurate and detailed explanation of photosynthesis, with a cosine similarity score of 0.8881 compared to the reference answer. The few-shot prompt is less accurate (0.6057), and the direct prompt is the least relevant (0.6601).
assignmen4.2.ipynb: The few-shot prompt consistently classifies sentiments correctly for all three texts. The basic and instruction prompts occasionally produce inconsistent or overly complex outputs.


