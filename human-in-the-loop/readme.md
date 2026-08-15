# AI-Powered Automated Content & Social Media Workflow (n8n)

An advanced, human-in-the-loop automated workflow built in **n8n** that leverages **Google Gemini AI**, **Tavily Search**, and **Gmail** to research, draft, review, revise, and manage content publishing pipelines autonomously.

## 🚀 Features

- **Automated Research:** Utilizes the Tavily Search tool via an AI Agent to fetch real-time, accurate, and current information based on your input topic.
- **AI Content Generation:** Uses Google Gemini chat models to craft engaging, concise, and structured posts.
- **Human-in-the-Loop Approval:** Sends the generated draft directly to your Gmail inbox (`sendAndWait` node) so you can review it before publishing.
- **Smart Text Classification:** Automatically classifies your email reply (`approved` or `rejected`) using a Text Classifier node.
- **Automated Revision Pipeline:** If a post is rejected or changes are requested, a dedicated Revision AI Agent takes your feedback, re-searches if needed, and rewrites the content.

---

## 🛠️ Workflow Architecture

1. **Trigger:** `On form submission` starts the workflow with a target topic.
2. **Data Preparation:** Formatted and structured using an `Edit Fields` node.
3. **Primary AI Agent:** Combines Google Gemini and Tavily Search to create the initial draft.
4. **Review & Notification:** A Gmail node waits for your review (`approved` / `reject`).
5. **Conditional Branching (`Text Classifier`):**
   - **Approved Route:** Delivers the finalized content to your inbox/publishing stage.
   - **Rejected Route:** Passes the feedback and original post to the **Revision Agent** to generate an improved version.

---

## 📋 Prerequisites & Setup

- **n8n** (Cloud or Self-Hosted)
- **Google Gemini API Key** (for chat models)
- **Tavily API Key** (for web search tool)
- **Gmail Account / Credentials** (for human review steps)

---

## ⚙️ How to Use

1. Import the workflow JSON into your n8n instance.
2. Set up your **Google Gemini** and **Tavily** credentials in the respective AI Agent nodes.
3. Configure your **Gmail** credentials for the review and notification steps.
4. Execute the workflow via a form submission, review the draft in your email, and reply with either `approved` or your feedback/rejection to test the automated loop!

---

## 👨‍💻 Author
**Muhammad Talha Ramzan**
