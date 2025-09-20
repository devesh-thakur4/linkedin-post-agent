# 🤖 LinkedIn Post Agent (n8n Workflow)

This n8n workflow automates the process of **generating, enhancing, and publishing LinkedIn posts with images**.  
It integrates **Google Drive, Tavily, Google Gemini, OpenAI, and LinkedIn APIs** to streamline your content automation.

---

## ✨ Features
- 🔔 **Google Drive Trigger** → Watches a folder for new images.  
- 📂 **File Handling** → Downloads, extracts, and processes files.  
- 🔎 **Tavily Search** → Fetches real-time web insights.  
- 🧠 **Google Gemini AI** → Generates high-quality LinkedIn post content.  
- 🖼️ **LinkedIn API** → Uploads images and creates posts automatically.  
- 📲 **Telegram Notifications** → Sends updates when images are uploaded.  
- ⏳ **Automation Loops & Waits** → Ensures smooth retries and scheduling.

---

## 🛠️ Setup Guide

**Author:** [Nate Herk](https://www.youtube.com/@nateherk)

This workflow requires configuration of multiple API credentials in **n8n**:

### ✅ Step 1: Set Up OpenRouter
1. Go to [openrouter.ai](https://openrouter.ai/)  
2. Generate an API key  
3. Add as a credential in n8n  

### ✅ Step 2: Tavily API
1. Create account at [tavily.com](https://tavily.com/)  
2. Get API key  
3. Add an HTTP credential in n8n  

### ✅ Step 3: Google Gemini (PaLM / Generative AI)
1. Visit [Google AI Platform](https://platform.openai.com/docs/overview)  
2. Get API key  
3. Add as `Google Palm API` credential in n8n  

### ✅ Step 4: LinkedIn & Gmail
- **LinkedIn:** Use OAuth2 or access token → to publish directly to your feed.  
- **Gmail (optional):** Send posts via email using the Gmail node.  

---

## ⚙️ Workflow Overview

```mermaid
flowchart TD
    A[📂 Google Drive Trigger] --> B[⬇️ Download File]
    B --> C[🔎 Tavily Search]
    C --> D[🧠 Google Gemini AI]
    D --> E[🖼️ Upload Image to LinkedIn]
    E --> F[✍️ Create LinkedIn Post]
    F --> G[⏳ Wait / Retry]
    A --> H[📲 Telegram Notification]
