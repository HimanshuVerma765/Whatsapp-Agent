🤖 My First Self-Replying WhatsApp AI Agent
Description
This project is a self-replying WhatsApp bot powered by an AI agent. It uses a combination of Docker, n8n, and a Node.js backend to handle incoming WhatsApp messages and generate intelligent responses. This guide will walk you through the essential steps to get your very own AI agent up and running!

Prerequisites
Before you begin, make sure you have the following installed on your machine:

Docker

Node.js and npm

Visual Studio Code (or your preferred code editor)

1️⃣ Run n8n with Docker
Start by pulling the n8n Docker image and running it. This will set up the environment for your workflow.

docker pull n8nio/n8n

Once the image is pulled, run the container.

# For macOS and Linux
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n

# For Windows (using Command Prompt)
docker run -it --rm ^
  -p 5678:5678 ^
  -v %USERPROFILE%\.n8n:/home/node/.n8n ^
  n8nio/n8n

You can now access n8n in your browser at: 👉 http://localhost:5678

2️⃣ Install Required Packages
Navigate to your project directory in the terminal and install the Node.js packages needed for your bot's code.

npm install express venom-bot axios

3️⃣ Set Up Your API Key
To enable your AI agent to communicate with the model, you'll need an API key.

Set up an account on Openrouter.

Add your API key to your n8n credentials.

4️⃣ Import Your Agent Workflow
Import your agent's workflow by uploading the provided .json file directly into your n8n dashboard. This will define the logic for how your agent responds to messages.

5️⃣ Run and Test Your Bot
Open your bot code in VS Code.

In n8n, Enable workflow testing.

Start your bot by running the following command in your terminal:

node bot.js

Trigger a test interaction using curl from a new terminal window to simulate a message:

curl -X POST http://localhost:3000/simulate-self \
  -H "Content-Type: application/json" \
  -d '{"body": "Hello there!", "from": "your-phone-number@c.us"}'

And you're all set! Your first AI agent is now ready to interact. Congratulations! 🎉

Contributing
We welcome contributions! If you have suggestions or find any issues, please feel free to open an issue or submit a pull request.

License
This project is licensed under the MIT License.