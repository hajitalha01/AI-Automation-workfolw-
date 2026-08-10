# 🤖 Customer Support Chatbot

An AI-powered customer support automation workflow built with **n8n**, **Gmail**, **Google Gemini**, and **Pinecone Vector Store**.

This chatbot automatically reads incoming customer emails, classifies them based on their intent, retrieves relevant business information from a knowledge base, and generates an appropriate customer support response.

---

## 🚀 Features

- 📩 Automatically receives incoming Gmail messages
- 🧠 Classifies customer emails using AI
- 🤖 Uses Google Gemini as the AI model
- 🔎 Retrieves relevant information from Pinecone Vector Store
- 📚 Uses a knowledge base to provide accurate responses
- 💰 Handles pricing and service-related questions
- 🤝 Handles AI Agent and AI Automation inquiries
- 📦 Handles order-related questions
- 🚫 Filters irrelevant emails
- ✉️ Automatically sends a response through Gmail
- 🧩 Uses Retrieval-Augmented Generation (RAG)

---

## 🏗️ Workflow Architecture

```text
Gmail Trigger
      │
      ▼
Text Classifier
      │
      ├── AI Agent / Automation Inquiry ──┐
      ├── Pricing / Services Inquiry ─────┤
      ├── Order / Purchase Inquiry ──────┤
      ├── Other / Not Relevant ──────────┤
      │                                   │
      ▼                                   ▼
   Relevant Emails                    Ignore
      │
      ▼
   AI Agent
      │
      ├── Google Gemini Chat Model
      │
      └── Pinecone Vector Store
                │
                ▼
          Knowledge Retrieval
                │
                ▼
          AI Generated Reply
                │
                ▼
          Gmail Send Message
