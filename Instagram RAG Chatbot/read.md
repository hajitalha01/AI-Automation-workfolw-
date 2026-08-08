# Instagram RAG Chatbot (n8n & Gemini)

An automated Instagram Direct Message (DM) chatbot built using **n8n**, **Google Gemini AI**, and **Pinecone Vector Store** for Retrieval-Augmented Generation (RAG). This bot allows businesses or fitness coaches to automatically answer customer queries using custom knowledge bases (such as PDFs stored in Google Drive) while maintaining conversation memory and logging user data to Google Sheets.

---

## Features

* **Instagram Integration:** Receives and responds to direct messages via Meta's Graph API webhooks.
* **RAG Architecture:** Utilizes Pinecone vector search to retrieve accurate context from uploaded documents (e.g., gym guidelines, FAQs, or business info) before generating replies.
* **AI Agent & Memory:** Powered by Google Gemini with window buffer memory to keep track of user conversation histories seamlessly.
* **Google Sheets Automation:** Automatically parses and appends user-specific data (such as name, age, weight, height, and BMI) directly into a connected Google Spreadsheet using AI tools.
* **Automated Knowledge Sync:** Watches a Google Drive folder/file for updates to keep the vector database synchronized with the latest documents.

---

## Workflow Architecture

1. **Webhook Trigger:** Listens for incoming messages from Instagram DMs.
2. **Switch & Routing:** Validates the message payload.
3. **AI Agent (Gemini):** Processes the incoming text, checks chat history via Simple Memory, and queries the Pinecone vector database tool for relevant information.
4. **Google Sheets Tool:** Extracts structural data to log user metrics when applicable.
5. **Formatting & HTTP Request:** Formats the AI response into plain text and sends it back to the user via the Instagram Graph API.

---

## Prerequisites & Credentials

To run or deploy this workflow, you will need the following credentials configured in your n8n instance:
* **Meta / Instagram Developer Account** (with a configured App, Page, and Instagram Business Account webhook).
* **Google Gemini API Account** (for LLM and Embeddings).
* **Pinecone Account** (Vector database index setup).
* **Google Sheets & Google Drive OAuth2 API credentials**.

---

## Setup Instructions

1. Import the `Instagram N8n Chatbot.json` file into your n8n workflow editor.
2. Connect your respective credentials for **Google Gemini**, **Pinecone**, **Google Sheets**, and **Instagram Graph API (HTTP Bearer Auth)**.
3. Update the Google Sheet ID and Pinecone index names to match your environment.
4. Set your Webhook URL in your Meta App settings for Instagram messaging.
5. Activate the workflow and test it by sending a DM to your connected Instagram account!
