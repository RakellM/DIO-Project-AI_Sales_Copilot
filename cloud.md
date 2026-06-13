# TasteCraft Agent - Cloud Deployment Configuration

## Runtime Environment
- **Platform:** Google Antigravity (free tier)
- **Alternative:** Open Code or Cloud Code (backup)

## LLM Configuration
- **Primary Model:** Gemini 3.5 Flash (free tier via Google AI Studio)
- **Fallback Model:** Gemini 1.5 Pro (if Flash unavailable)
- **Temperature:** 0.3 (consistent, repeatable responses)
- **Max Output Tokens:** 2048

## Environment Variables
```bash
AGENT_NAME=TasteCraft_Sales_Copilot
AGENT_VERSION=1.0.0
KNOWLEDGE_PATH=/knowledge
RESPONSE_FORMAT=structured_3_sections
CANADIAN_CONTEXT_ENABLED=true
```

## API Configuration (Gemini)
```bash
api_provider: google_ai_studio
model: gemini-3.5-flash
free_tier_limits:
  requests_per_minute: 60
  requests_per_day: 1000
  context_window: 128000_tokens
setup_url: https://aistudio.google.com
```

## Memory Settings
- Conversation memory: Last 5 exchanges (sliding window)
- Knowledge refresh: Query reads fresh markdown files each time
- Session persistence: 30 minutes inactivity timeout

## Deployment Instructions (For Google Antigravity)

Step 1 - Import this repository into Antigravity:
In Antigravity terminal run:
```bash
git clone https://github.com/yourusername/tastecraft-ai-copilot.git
cd tastecraft-ai-copilot
```

Step 2 - Set Gemini API key (free):
- Go to https://aistudio.google.com
- Create API key (no billing required)
- In Antigravity: Settings → Secrets → Add GEMINI_API_KEY

Step 3 - Run the agent:
```bash
deagent run --config agents.md --runtime antigravity
```

## Alternative Runtimes (Free)

Open Code: `deagent run --config agents.md --runtime opencode`
Cloud Code: `deagent run --config agents.md --runtime cloudcode`

## Cost Analysis
- Gemini API: $0 (free tier covers demos and small team testing)
- Antigravity compute: $0 (Google free tier)
- Storage: $0 (GitHub free tier)
- Total monthly cost: $0

Free tier sufficiency: For a sales team of 5 reps each asking 20 questions/day = 100 requests/day < 1000 limit

## Troubleshooting

Problem: "Gemini API key missing"
Solution: Add key in Antigravity Settings → Secrets

Problem: "Knowledge files not found"
Solution: Ensure `/knowledge/` folder contains all 4 markdown files

Problem: "Rate limit exceeded"
Solution: Wait 1 minute. Free tier: 60 requests/minute.

Problem: "Agent not following 3-section format"
Solution: Check that [`agents.md`](./agents.md) priority rules are at the top of the file


---

## Authentication

For **Antigravity CLI**: Sign in with Google account (OAuth). No API key required.

For **Antigravity IDE**: Use GEMINI_API_KEY environment variable or MCP config.
