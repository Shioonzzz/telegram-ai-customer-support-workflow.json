# AI-Powered Telegram Customer Support Automation (n8n)

## Overview
This project demonstrates an AI-assisted customer support automation built with **n8n**.  
The workflow processes incoming Telegram messages, attempts rule-based FAQ resolution, classifies customer intent and urgency using a Large Language Model (LLM), and conditionally escalates conversations to human agents.

The primary goal of this project is to showcase **automation design, decision logic, and practical AI integration**, rather than building a fully production-ready customer support product.

---

## Key Features
- Telegram webhook-based message ingestion
- Structured customer data extraction
- Rule-based FAQ matching to reduce unnecessary AI calls
- LLM-powered intent, priority, and sentiment classification
- Conditional routing between auto-reply and human escalation
- Automated customer responses
- Interaction logging to Google Sheets for audit and analysis

---

## System Architecture
The workflow follows a **decision-first approach**:

1. Incoming messages are received via a Telegram Trigger
2. Customer data is normalized and extracted
3. Messages are checked against an FAQ database (Google Sheets)
4. If no FAQ match is found, the message is sent to an LLM for classification
5. Based on classification results:
   - Simple cases receive automated replies
   - High-priority or complex cases are escalated to human agents
6. All interactions are logged for traceability

Architecture diagrams and workflow screenshots are available in the `docs/` directory.

---

## Design Decisions
- **FAQ-first logic** is used to minimize AI usage, cost, and latency
- AI is applied for **classification and suggestion**, not for autonomous decision-making
- Human escalation is determined by intent and priority rather than sentiment alone
- The workflow prioritizes **readability, explainability, and debuggability**
- Advanced features such as long-term conversational memory are intentionally excluded to keep the system maintainable and easy to reason about

---

## Limitations
- No long-term conversational memory across messages
- Single-language response output
- Limited intent taxonomy
- AI classification does not include confidence scoring

---

## Possible Improvements
- Conversation memory using a database or vector store
- Multilingual message handling
- Confidence-based routing for AI classification
- More advanced reply personalization
- Centralized status normalization for easier scaling

---

## Tech Stack
- **n8n** – Workflow automation
- **Telegram Bot API** – Message ingestion and replies
- **Google Gemini (LLM)** – Message classification
- **Google Sheets** – FAQ storage and interaction logging

---

## Disclaimer
This project is intended for **portfolio and learning purposes**.  
It demonstrates system design and automation logic rather than a fully production-hardened customer support solution.
