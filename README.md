## Code & files
To run the code, upload the data files from a folder named "data" in the Colab environment and set up the necessary key. 📌[Colab](https://colab.research.google.com/drive/1_TYG8saveyjD1yY4RKJRxZfFySosIW6Q)

# About
![RAG Flyer Page 1](./RAG%20Flyer_page-1.jpg)
![RAG Flyer Page 2](./RAG%20Flyer_page-2.jpg)

## RAG Chatbot for Carlson School of Management

Traditional generative AI systems are prone to hallucinations and cannot access information beyond their training cutoff. This project builds a Retrieval-Augmented Generation (RAG) chatbot for the Carlson School of Management's website, grounding the language model's responses in verified, retrieved content rather than relying solely on parametric memory.

---

## Problem Statement

Prospective students, current enrollees, and faculty frequently query the Carlson School's website for program details, admissions requirements, faculty profiles, and events. A standard chatbot would either hallucinate incorrect answers or fail to surface up-to-date information. The goal is to build a chatbot that retrieves relevant content from the Carlson website and generates accurate, grounded responses using a large language model.

---

## Scope of Work

- Manually collect and curate relevant content from the Carlson School website
- Embed the text data into dense vector representations using an embedding model
- Index the embeddings into a vector database configured for real-time similarity search
- Connect Google's Gemini LLM to the vector database for retrieval-augmented response generation
- Build a user-facing demo interface using Voila
- Evaluate chatbot reliability, accuracy, and responsiveness

---

## How I Achieved It

Data was manually fetched from the Carlson School website due to its complex JavaScript-rendered structure, which made automated scraping unreliable. The collected text was chunked, embedded, and indexed into a vector database. At inference time, a user query is embedded with the same model, and the top-k most semantically similar document chunks are retrieved. These chunks are passed as context to Gemini, which generates a response grounded in the retrieved content. The demo was deployed as a Voila interactive notebook.

Note: Real-time data ingestion was not implemented in this version. The vector database reflects a static snapshot of the website. Future enhancements could include automated scraping pipelines for continuous updates.

---

## Technical Stack

- Language Model: Google Gemini
- Vector Database: Embedded vector store (indexed on Colab)
- Embedding: Text embedding model (vectorized Carlson website content)
- Interface: Voila (Jupyter-based interactive UI)
- Platform: Google Colab

---

## Business Applications

- Healthcare: Retrieve from clinical knowledge bases to assist medical staff with patient summaries and research
- E-commerce: Answer product, warranty, and order queries using real-time catalog data
- Human Resources: Respond to policy questions by grounding answers in company handbooks and HR documentation

---

## Results

The RAG chatbot successfully answered queries about Carlson School programs, admissions, and events using retrieved website content. Responses were factually grounded and avoided hallucinations present in a base Gemini comparison. The Voila interface provided a usable demo environment for stakeholder presentations.

The comparison below illustrates RAG's advantages over standard generative AI:

| Feature              | Traditional AI                     | RAG                                          |
|----------------------|------------------------------------|----------------------------------------------|
| Data Source          | Static, pre-trained knowledge      | Dynamic, real-time retrieval                 |
| Accuracy             | Prone to hallucinations            | Grounded and factually accurate              |
| Update Frequency     | Requires retraining for updates    | Retrieves latest indexed information         |
| Cost Efficiency      | High retraining costs              | Eliminates need for expensive retraining     |

