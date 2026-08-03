# 🍽️ Restaurant RAG Chatbot with n8n, Gemini & Pinecone

An AI-powered Restaurant Chatbot built using **n8n**, **Google Gemini Embeddings**, **Google Gemini Chat Model**, and **Pinecone Vector Database**.

The chatbot uses Retrieval-Augmented Generation (RAG) to answer restaurant-related questions from PDF documents such as menus, restaurant information, pricing, timings, and contact details.

---

## 🚀 Features

- PDF Knowledge Base
- Retrieval-Augmented Generation (RAG)
- Google Gemini Embeddings
- Google Gemini Chat Model
- Pinecone Vector Database
- Semantic Search
- Restaurant Question Answering
- Built with n8n (Low-Code AI Workflow)

---

## 🛠 Tech Stack

- n8n
- Google Gemini API
- Pinecone Vector Database
- Gemini Embeddings
- Gemini Chat Model
- PDF Data Loader

---

## 📌 Workflow

### Document Ingestion

PDF → Data Loader → Gemini Embeddings → Pinecone Vector Store

### Question Answering

User Question → Vector Store Retriever → Pinecone → Gemini Chat Model → Final Answer

---

## Example Questions

- What are the restaurant opening hours?
- What is the restaurant address?
- What payment methods are accepted?
- Does the restaurant offer home delivery?
- What is the seating capacity?
- What food items are available?

---

## Project Structure

```
.
├── workflow.json
├── README.md
<img width="563" height="282" alt="image" src="https://github.com/user-attachments/assets/dd5ca28b-1679-405b-862f-f540acd36597" />

```

---

## Installation

1. Clone the repository


2. Import the workflow into n8n.

3. Configure:

- Google Gemini API Key
- Pinecone API Key

4. Create a Pinecone index with the correct embedding dimensions.

5. Run the ingestion workflow.

6. Start chatting with your Restaurant AI Assistant.

---

## Future Improvements

- Conversation Memory
- Multi-PDF Support
- Multiple Restaurants
- Voice Chat
- WhatsApp Integration
- Telegram Bot
- Website Widget
- Admin Dashboard

---

## Author

**Muhammad Talha Ramzan**

BS Artificial Intelligence Student

Built with ❤️ using n8n, Gemini, and Pinecone.
