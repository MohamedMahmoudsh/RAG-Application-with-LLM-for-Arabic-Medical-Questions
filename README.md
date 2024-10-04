# RAG Application with LLM for Arabic Medical Questions

This repository implements a **Retrieval-Augmented Generation (RAG) application** with a **Large Language Model (LLM)** to handle Arabic medical questions. The data contains question-answer pairs from 20 different medical specialties, and we focus specifically on **internal medicine**. The system retrieves relevant information using a **vector database** and generates accurate responses using a prompt-based approach.

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Installation](#installation)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Gradio Interface](#gradio-interface)
- [Notes](#notes)
- [Credits](#credits)

## Project Overview

The purpose of this project is to develop a **RAG model** using a Large Language Model (LLM) that specializes in answering questions about **internal medicine** in Arabic. The system:
1. Retrieves relevant medical information from a vector database.
2. Generates human-like responses to questions using an LLM.
3. Focuses on internal medicine questions and provides accurate, informative answers.

To ensure high-quality responses, the application uses a prompt-based approach. If the system cannot confidently answer a question, it advises the user to consult a physician.

### Data Sources
1. **Original Dataset**: [Arabic Medical Questions Dataset](https://www.kaggle.com/datasets/mohamedmahmod/ragdata)
   - Contains question and answer pairs from 20 different medical specialties.
   
2. **Vector Database**: [Vectorized Internal Medicine Data](https://www.kaggle.com/datasets/mohamedmahmod/vectorragdata)
   - Converted internal medicine questions into vector embeddings for retrieval.

## Installation

1. Clone the repository:

    ```bash
    git clone [https://github.com/your-repo-link.git](https://github.com/MohamedMahmoudsh/RAG-Application-with-LLM-for-Arabic-Medical-Questions)
    cd your-repo-link
    ```

2. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. Download the datasets:
    - The question-answer dataset can be found on Kaggle [here](https://www.kaggle.com/datasets/mohamedmahmod/ragdata).
    - The vector database is available [here](https://www.kaggle.com/datasets/mohamedmahmod/vectorragdata).

4. Place the downloaded datasets in the appropriate directories in your project folder.

## How It Works

### 1. **Data Preprocessing:**
   - The dataset contains Arabic medical questions and answers for 20 specialties. We focus on **internal medicine** and chunk the data into smaller, meaningful sections.
   - The **internal medicine** questions are vectorized using an open-source Arabic embedding model, which enables efficient similarity-based retrieval.

### 2. **Vector Database:**
   - The vectorized data is stored in **Chroma**, a vector database that allows fast search and retrieval of relevant text chunks based on the user’s query.

### 3. **LLM for Answer Generation:**
   - The system uses **ChatGroq LLM** with a specific prompt format designed for internal medicine. If there is uncertainty in the information, the system recommends visiting a doctor.

### 4. **Retrieval-Augmented Generation (RAG):**
   - The LLM uses the retrieved vectorized chunks to generate accurate answers to user queries.
   - The user query is combined with the retrieved context to provide a final response.


## Usage

To use the application locally, follow these steps:

1. **Run the Gradio Interface:**

    ```bash
    python app.py
    ```

2. Once the app starts, you can enter Arabic medical questions related to internal medicine, and the system will provide answers using the LLM and the retrieved context from the vector database.

## Gradio Interface

The application is integrated with **Gradio** to provide an interactive user interface. Here’s how the interface works:
1. The user enters their **internal medicine** question in Arabic.
2. The system retrieves the top 5 relevant chunks from the vector database.
3. The LLM generates a response based on the retrieved context.
4. The interface shows both the final answer and the question used in the prompt for transparency.

## Notes

- The **ChatGroq LLM** is used for answer generation.
- The model only provides medical information for **internal medicine** and may advise consulting a physician if the question is outside its scope.
- The **vector database** stores the vectorized data for internal medicine.

## Credits

This project was developed by **Mohamed Mahmoud** as part of a specialized application in the medical field.

- [Arabic Medical Questions Dataset](https://www.kaggle.com/datasets/mohamedmahmod/ragdata)
- [Vectorized Internal Medicine Data](https://www.kaggle.com/datasets/mohamedmahmod/vectorragdata)


