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

🔄 How It Works
1. Gmail Trigger

The workflow starts when a new email is received in Gmail.

The incoming email content is passed to the AI classification system.

2. Text Classification

The incoming email is analyzed by an AI-powered Text Classifier.

Emails are categorized based on their intent, such as:

AI Agent / Automation Inquiry
Pricing / Services Inquiry
Order / Purchase Inquiry
Other / Not Relevant

This allows the workflow to separate potential customer inquiries from irrelevant emails.

3. AI Agent

Relevant customer emails are sent to the AI Agent.

The AI Agent understands the customer's question and determines what information is required to provide an accurate response.

4. Pinecone Vector Store

The AI Agent is connected to a Pinecone Vector Store containing the company's knowledge base.

The vector database can contain information such as:

AI Agent services
AI Automation services
Service descriptions
Features
Pricing
Packages
Quotes
Orders
Business processes
Frequently asked questions
Company policies

The AI Agent retrieves the most relevant information from Pinecone before generating a response.

5. Google Gemini

Google Gemini is used as the AI language model for:

Email classification
Understanding customer intent
Processing retrieved knowledge
Generating natural customer support responses
6. Automatic Gmail Response

After retrieving the relevant information and generating a response, the workflow sends the reply automatically through Gmail.

The customer receives a natural and professional email response without manual intervention.

🧠 RAG Architecture

This project uses Retrieval-Augmented Generation (RAG).

Instead of allowing the AI to answer company-specific questions using only its general knowledge, the AI first retrieves relevant information from the Pinecone Vector Store.

Customer Question
       │
       ▼
   AI Agent
       │
       ▼
Pinecone Vector Search
       │
       ▼
Relevant Knowledge
       │
       ▼
Google Gemini
       │
       ▼
Accurate Customer Response

This helps reduce hallucinations and allows the chatbot to answer questions based on the company's actual information.

🛡️ Knowledge Base Rules

The AI Agent is instructed to:

Use the knowledge base for company-related questions.
Retrieve relevant information before answering.
Never invent prices or services.
Never guess missing information.
Never create unsupported policies or features.
Use the most relevant retrieved information.
Ask the team to confirm information when the knowledge base does not contain an answer.
🛠️ Technologies Used
Technology	Purpose
n8n	Workflow automation
Gmail	Receive and send customer emails
Google Gemini	AI model
Pinecone	Vector database
Embeddings	Convert knowledge into searchable vectors
RAG	Retrieve knowledge before generating responses
📌 Example Use Cases
AI Agent Inquiry

Customer:

Hi, I am interested in an AI agent for my business. What can you provide?

The system:

Receives the email.
Classifies it as an AI Agent inquiry.
Sends it to the AI Agent.
Searches Pinecone for relevant AI Agent information.
Generates a response.
Sends the response through Gmail.
Pricing Inquiry

Customer:

How much does your AI automation service cost?

The system retrieves pricing information from the knowledge base and generates a response.

If pricing information is not available, the AI is instructed not to guess the price.

Irrelevant Email

Customer:

Subscribe to our newsletter and get our latest marketing offers.

The classifier can categorize the message as:

Other / Not Relevant

and the email can be excluded from the customer-support response workflow.

🔐 Environment Variables / Credentials

The workflow requires credentials for the services being used.

Typical credentials include:

Gmail OAuth credentials
Google Gemini API credentials
Pinecone API credentials

Never upload API keys, passwords, OAuth secrets, or private credentials to GitHub.

Use n8n credentials or environment variables instead.

📂 Knowledge Base

The Pinecone Vector Store should contain verified company information.

Recommended knowledge-base content:

Company Information
Services
AI Agent Services
AI Automation Services
Pricing
Packages
Features
Order Process
FAQs
Policies
Customer Support Information

Only verified business information should be added to the knowledge base.

⚠️ Important Notes
Gemini API Rate Limits

Google Gemini API usage is subject to rate limits and quotas.

During development/testing, repeatedly executing the workflow can cause 429 Too Many Requests errors if the API quota is exceeded.

For production usage, configure an appropriate Gemini API plan and monitor API usage.

Pinecone

Pinecone is used for semantic retrieval of company knowledge.

The quality of the chatbot's responses depends heavily on the quality and accuracy of the documents stored in the vector database.

🎯 Future Improvements

Possible improvements include:

 Add conversation memory
 Add customer history
 Add human-agent escalation
 Add CRM integration
 Add automatic follow-up emails
 Add multilingual support
 Add sentiment analysis
 Add analytics dashboard
 Add ticket creation
 Add WhatsApp integration
 Add Slack notifications for important leads
 Add lead scoring
👨‍💻 Project Purpose

This project demonstrates how AI, vector databases, and workflow automation can be combined to build an automated customer support system.

The goal is to reduce manual email handling while providing customers with fast, relevant, and knowledge-based responses.

📜 License

This project is for educational and demonstration purposes.

Add your preferred license here if you plan to make the project open source.


### GitHub par files ka structure

Main recommend karunga:

```text
customer-support-chatbot/
│
├── README.md
├── workflow/
│   └── customer-support-chatbot.json
├── knowledge-base/
│   └── knowledge-base.pdf
└── screenshots/
    └── workflow.png

Important: GitHub par .json workflow upload karte waqt apni Gmail credentials, Gemini API key, Pinecone API key ya secrets hard-code karke upload mat karna.
