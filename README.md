🚀 AI-Driven Development – Task 6
GitHub × MCP Integration (Hosted Method)

This project demonstrates how to integrate GitHub MCP Server with the Google Gemini CLI using a Hosted MCP Server (no installation, no Docker required).
After completing this setup, Gemini can list, read, and interact with GitHub repositories.

📌 Features

🔗 Connect GitHub → Gemini using a secure hosted MCP server

🔐 Token stored safely in .env (not in JSON)

⚡ No Docker required

🧩 Supports 90+ GitHub tools

📁 Fully compatible with Gemini MCP Framework

📂 Project Structure
project-folder/
│
├── .env                # Secure GitHub token (NOT uploaded to GitHub)
├── settings.json       # MCP configuration
├── screenshots/        # (Optional) Submission screenshots
└── README.md           # Project documentation

🛠️ Step-by-Step Setup
✅ 1. Create GitHub Personal Access Token (PAT)

Open: https://github.com/settings/personal-access-tokens/new

Generate a token with:

✔ repo (Full Read/Write)

Copy the token (GitHub shows it once).

✅ 2. Create .env File (Stores Token Securely)

Run in terminal:

mkdir -p ~/.config/google-mcp
nano ~/.config/google-mcp/.env


Add:

GITHUB_TOKEN=ghp_yourTokenHere

✅ 3. Configure settings.json

Create or edit:

~/.config/google-mcp/settings.json


Paste:

{
  "mcpServers": {
    "github": {
      "url": "https://mcp-github-server.glitch.me",
      "environment": {
        "GITHUB_TOKEN": "${GITHUB_TOKEN}"
      }
    }
  }
}

✅ 4. Restart Gemini CLI
gemini

✅ 5. Verify MCP Connection
/mcp list


Expected:

🟢 github — Ready (90+ tools)

✅ 6. Test GitHub Integration

Ask Gemini:

List my GitHub repositories


If Gemini lists your repos → 🏆 Integration Successful
