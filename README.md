# ai-sales-crm
AI-Powered Sales CRM (MVP)

A simple, Docker-ready AI Sales CRM that runs entirely on your own machine — no external API costs.
It uses local LLMs (Ollama / Groq) to score and prioritize leads, enrich missing details, suggest buyer personas,
draft personalized outreach emails, and track campaign performance automatically.

⚡ Quick Start (Demo)
--------------------------------

✅ Ready to launch your own AI-powered sales workflow?
* cd ai-sales-crm
* docker compose up --build


Here’s what happens:
1. Loads 25+ sample leads from data/leads.csv
2. AI model scores, enriches, and builds personas for each lead
3. Personalized outreach emails are generated using Ollama
4. Emails are sent to MailHog (http://localhost:8025)
5. Results (personas, priorities, and email status) are saved to data/leads_out.csv
6. A campaign summary report is created under reports/

Access Points:
- MailHog UI → http://localhost:8025
- Ollama API → http://localhost:11434
- Reports → reports/report-*.md

⚙️ Configuration
--------------------------------
You can tweak settings in `.env` if you want custom behavior.

Restart after editing:
docker compose down
docker compose up --build

📁 Using Your Own Leads
--------------------------------
Replace sample CSV with your own data in data/leads.csv.

Once processed, you’ll get data/leads_out.csv with:
- Lead score (1–100)
- Priority level (High/Medium/Low)
- Suggested persona
- Email status + timestamps
- Generated email text



🧰 Common Issues
--------------------------------
| Problem | Solution |
|----------|-----------|
| No emails in MailHog | Check SMTP settings |
| Slow AI replies | Use smaller model |
| GPU not used | Enable OLLAMA_FORCE_GPU |
| CSV not updating | Check data folder permissions |
| Out of memory | Use lighter model or increase Docker memory |




