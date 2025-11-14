# AI-Powered WooCommerce Shopping Assistant (n8n + OpenAI)

This repository contains an n8n workflow that turns your WooCommerce store into an **AI-powered shopping assistant**.

The workflow connects:

- A chat entry point (webhook-based chat trigger)
- An AI Agent powered by OpenAI
- A short-term memory component
- A WooCommerce tool that fetches products in real time

Customers can ask natural-language questions like:

> "Do you have black sneakers in size 42?"  
> "What are your cheapest phones under 100k?"  

and the AI will use your **live WooCommerce catalogue** to answer.

---

## ✨ Features

- 🧠 **AI Agent** – Handles user intent and generates natural replies.
- 🛒 **WooCommerce integration** – Uses your real products (name, price, etc.).
- 💬 **Chat trigger** – Can be connected to a website chat, API, or any frontend.
- 🧩 **Composable** – You can extend it with more tools (orders, carts, recommendations).
- 🧱 **Prompt-architecture friendly** – Great starting point for AI engineering & automation experiments.

---

## 🧰 Requirements

You’ll need:

1. **n8n** (self-hosted or n8n Cloud)  
2. **OpenAI account & API key**  
3. **WooCommerce store** with REST API enabled  
4. **n8n credentials** for:
   - OpenAI (`OpenAI API` credential)
   - WooCommerce (`WooCommerce API` credential)

> 🔐 **No secrets are included in this repo.**  
> You MUST configure your own credentials in your n8n instance.

---

## 📁 Files

- `workflow.json` – The n8n workflow you can import.
- `README.md` – This file.

---

## 🚀 Setup Guide

### 1. Install or access n8n

You can use:

- **n8n Cloud**, or  
- Self-hosted n8n (Docker, Node, etc.)

Follow the official n8n docs for installation if you don’t have an instance yet.

---

### 2. Create your credentials in n8n

#### a) OpenAI credential

1. In n8n, go to **Settings → API Credentials** (or Credentials in the left menu).
2. Create a new **OpenAI API** credential.
3. Paste your **OpenAI API key**.
4. Save it and remember the **name** you used (e.g. `OpenAI - Main`).

#### b) WooCommerce credential

1. In WooCommerce, go to **WooCommerce → Settings → Advanced → REST API**.  
2. Create a new API key with **Read** permissions (or more if you plan to extend this).
3. Copy the **Consumer Key** and **Consumer Secret**.
4. In n8n, create a new **WooCommerce API** credential and:
   - Set your **store URL** (e.g. `https://yourstore.com`)
   - Paste the consumer key & secret
5. Save and remember the **credential name**.

> ⚠️ Never commit your API keys or credentials to GitHub.

---

### 3. Import the workflow

1. Download `workflow.json` from this repo.
2. In n8n, go to **Workflows → Import from File**.
3. Select `workflow.json` and import it.
4. Open the workflow.

---

### 4. Attach your credentials inside the workflow

Because credentials are instance-specific, the JSON uses placeholders:

```json
"openAiApi": {
  "id": "REPLACE_WITH_YOUR_OPENAI_CREDENTIAL_ID_IN_N8N",
  "name": "REPLACE_WITH_YOUR_OPENAI_CREDENTIAL_NAME_IN_N8N"
}


"wooCommerceApi": {
  "id": "REPLACE_WITH_YOUR_WOOCOMMERCE_CREDENTIAL_ID_IN_N8N",
  "name": "REPLACE_WITH_YOUR_WOOCOMMERCE_CREDENTIAL_NAME_IN_N8N"
}


