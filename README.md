# AI-Powered WooCommerce Shopping Assistant (n8n + OpenAI)

This repository contains an **n8n automation workflow** that turns any WooCommerce store into an **AI-powered shopping assistant**.  
It uses OpenAI, WooCommerce REST API, and n8n's AI Agent node to understand customer queries and respond with real product data.

With this workflow, customers can ask natural-language questions like:

> "Do you have black sneakers in size 42?"  
> "What are your cheapest phones under 100k?"  
> "Show me your latest laptops under ₦300k."

The AI agent will read your **live WooCommerce catalogue**, fetch product information, and respond instantly with intelligent answers.

---

## ✨ Features

- 🧠 **AI Agent** – Handles user intent and generates natural replies.  
- 🛒 **WooCommerce integration** – Reads real-time product data from your store.  
- 💬 **Chat trigger** – Works with any chat UI, webhook, API, or front-end.  
- 🧩 **Composable design** – Extend with more agents or tools (orders, carts, upsells).  
- 🔁 **Memory Engine** – Maintains short-term conversation memory.  
- ⚡ **Automation-ready** – Ideal for AI engineering, prompt architecture, and workflow automation projects.

---

## 🧰 Requirements

You’ll need:

1. **An n8n instance** (self-hosted or n8n Cloud)  
2. **OpenAI account & API key**  
3. **A WooCommerce store** with REST API enabled  
4. **Two credentials in n8n**:  
   - `OpenAI API`  
   - `WooCommerce API`  

> 🔐 **Important:**  
> No API keys, secrets, or credentials are included in this repository.  
> You must configure these in your own n8n environment.

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `workflow.json` | The exported n8n workflow (clean, sanitized, ready to import) |
| `README.md` | Full setup and usage documentation |

---

## 🚀 Setup Guide

### 1. Install or access n8n

Use either:

- **n8n Cloud** (recommended for beginners)  
- **Self-hosted n8n** (Docker, PM2, or Node)

Official installation guide:  
https://docs.n8n.io/hosting/

---

## 2. Create Credentials in n8n

### a) OpenAI Credential

1. In n8n, go to **Credentials**  
2. Create a new credential of type **OpenAI API**  
3. Add your **OpenAI API Key**  
4. Save and note the credential name  

### b) WooCommerce Credential

1. In WordPress, go to:  
   **WooCommerce → Settings → Advanced → REST API**  
2. Create a new key with **Read** permission  
3. Copy the **Consumer Key** and **Consumer Secret**  
4. In n8n, create a **WooCommerce API** credential:  
   - Add your **Store URL**  
   - Add the Consumer Key  
   - Add the Consumer Secret  
5. Save and note the credential name  

> ⚠️ Never upload API keys to GitHub or expose them publicly.

---

## 3. Import the Workflow into n8n

1. Download `workflow.json` from this repository  
2. In n8n:  
   **Workflows → Import from File**  
3. Select the JSON file and import  
4. Open the workflow  

---

## 4. Attach Your Credentials

The JSON includes credential placeholders such as:

```json
"openAiApi": {
  "id": "REPLACE_WITH_YOUR_OPENAI_CREDENTIAL_ID_IN_N8N",
  "name": "REPLACE_WITH_YOUR_OPENAI_CREDENTIAL_NAME_IN_N8N"
},
"wooCommerceApi": {
  "id": "REPLACE_WITH_YOUR_WOOCOMMERCE_CREDENTIAL_ID_IN_N8N",
  "name": "REPLACE_WITH_YOUR_WOOCOMMERCE_CREDENTIAL_NAME_IN_N8N"
}
