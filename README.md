# 🤖 My First Self-Replying WhatsApp AI Agent

## Description

This project is a self-replying WhatsApp bot powered by an AI agent. It leverages **Docker**, **n8n**, and a **Node.js backend** to handle incoming WhatsApp messages and generate intelligent responses.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Docker** - Container platform
- **Node.js** and **npm** - JavaScript runtime and package manager
- **Visual Studio Code** (or preferred code editor)

## Installation & Setup

### 1️⃣ Run n8n with Docker

First, pull the n8n Docker image:

```bash
docker pull n8nio/n8n
```

Then run the container:

**For Windows:**

```cmd
docker run -it --rm ^
  -p 5678:5678 ^
  -v %USERPROFILE%\.n8n:/home/node/.n8n ^
  n8nio/n8n
```

Access n8n dashboard at: [http://localhost:5678](http://localhost:5678)

### 2️⃣ Install Dependencies

```bash
npm install express venom-bot axios
```

### 3️⃣ API Configuration

1. Create an account on [OpenRouter](https://openrouter.ai)
2. Configure your API key in n8n credentials
3. Verify API access

### 4️⃣ Workflow Setup

1. Open n8n dashboard
2. Import the provided `.json` workflow file
3. Configure webhook endpoints

### 5️⃣ Launch & Testing

1. Start the bot:

```bash
node bot.js
```

2. Test with a sample request:

```bash
curl -X POST http://localhost:3000/simulate-self ^
  -H "Content-Type: application/json" ^
  -d "{\"body\": \"Hello there!\", \"from\": \"your-phone-number@c.us\"}"
```

## Quick Start Guide

1. Install prerequisites
2. Run n8n container
3. Set up API credentials
4. Import workflow
5. Launch bot
6. Send test message
