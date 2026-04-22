# Module 1: India Bootcamp Developer Environment Setup

## Overview
This module sets up a **zero-cost, free-tier** development environment optimized for India interns using Google Colab (no local install friction) + graze-cli (agentic coding tool).

**Goals:**
- Run graze in Colab (free-tier Groq/Gemini)
- Access Open Paws tools (graze guide, herd status)
- Submit first Guild quest by end of bootcamp

## Step 1: Google Colab + graze install
```bash
!curl -fsSL https://cli.openpaws.ai/install | bash
!graze --version
```

## Step 2: Free-tier API keys
- [Groq free tier](https://console.groq.com) → `GROQ_API_KEY`
- [Gemini free tier](https://makersuite.google.com/app/apikey) → `GOOGLE_GENERATIVE_AI_API_KEY`
- Colab secrets: Runtime → Manage secrets → Add keys

## Step 3: Test graze
```bash
!graze herd status
!graze guide testing
```

## Step 4: First quest scaffold
Create `first-tool.py` notebook:
```python
# Your first advocacy tool
print(\"Hello from India bootcamp!\")
```

## Next: Module 2 (hands-on tools)
