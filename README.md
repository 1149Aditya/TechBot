# TechBot - AI Assistant for Data Science & Machine Learning Students

**TechBot** is an AI-powered chatbot designed to assist students enrolled in Data Science, Machine Learning, and Artificial Intelligence courses. The bot helps students by answering questions related to the course materials, assignments, and resources. TechBot leverages LangChain and FAISS for intelligent document retrieval and conversation management. 

---

## Tech Stack

- **LangChain**: Framework used for developing AI-powered chatbots.
- **FAISS**: A library for efficient similarity search, used to store and retrieve document embeddings.
- **HuggingFace Embeddings**: Provides sentence embeddings to convert documents into vector form for FAISS.
- **MongoDB**: Used for storing chat history and user interactions.
- **Streamlit**: Web framework for creating the user interface.
- **Python**: Primary programming language.

---

## Installation

### Prerequisites

Ensure you have the following installed:

- Python 3.8 or later
- MongoDB (if using local database)
- HuggingFace API Token (for LLM model access)
- FAISS (for document vector storage)

### Setup Instructions

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/TechBot.git
    cd TechBot
    ```

2. Install required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. Set up the environment variables in your `.env` file:

    ```
    HF_TOKEN=your_huggingface_api_token
    ```

4. Set up MongoDB (or Firebase/PostgreSQL) for storing chat history.
   
   For MongoDB, ensure it's running locally:

    ```bash
    docker run --name mongodb -d -p 27017:27017 mongo
    ```

5. Prepare the FAISS Vectorstore with your course materials:

    - Place the PDFs (or other course-related documents) in the `data/` directory.
    - Run the `create_memory_for_llm.py` script to generate document embeddings and store them in FAISS.

    ```bash
    python create_memory_for_llm.py
    ```

6. Launch the TechBot app:

    ```bash
    streamlit run techbot.py
    ```

---

## Usage

- Open the chatbot interface to ask questions related to your Data Science, Machine Learning, and AI courses.
- The bot will retrieve relevant information from the course materials (PDFs) and provide answers based on that context.
- You can view past chats and load them for easy reference.
- New conversations will be saved in MongoDB for future use.



