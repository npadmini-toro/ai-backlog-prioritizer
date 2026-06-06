# AI Backlog Prioritizer
**A Product Owner tool powered by Claude AI + RICE Framework**

> Live demo: [https://ai-backlog-prioritizer-8bytbszzvfxubscmwokwyj.streamlit.app/](https://ai-backlog-prioritizer-8bytbszzvfxubscmwokwyj.streamlit.app/)

## Problem Statement
Product Owners spend significant time manually scoring and defending 
backlog prioritization decisions. Stakeholders challenge rankings without 
data. This tool uses Claude AI to score every story using the RICE 
framework — and lets the PO challenge any decision in plain English, 
keeping the human in control.

## What It Does
- Accepts any Jira CSV export as input
- Scores each story using RICE (Reach, Impact, Confidence, Effort)
- Ranks stories from highest to lowest priority
- Explains reasoning for every ranking decision
- Lets PO challenge any score in plain English
- Exports final prioritized backlog to CSV

## Product Decisions I Made (Why This Is a PO Project)
| Decision | What I chose | Why |
|----------|-------------|-----|
| Scoring framework | RICE | More quantifiable and defensible than MoSCoW |
| Human-in-the-loop | Chat challenge interface | PO always has final say — AI assists, not decides |
| Input format | Jira CSV export | Works with real backlogs, no manual data entry |
| Context input | Free text PO notes | Lets PO guide scoring with sprint goals and constraints |
| Export | CSV download | Prioritized backlog goes back into Jira easily |

## Acceptance Criteria (Written Before Coding)
- [ ] Given a CSV is loaded, When Prioritize is clicked, Then RICE scores appear in < 20s
- [ ] Given scores appear, Then every story has a reasoning explanation
- [ ] Given PO types a challenge, Then Claude responds with updated reasoning
- [ ] Given prioritization is complete, Then PO can export to CSV
- [ ] Given PO context is provided, Then scores reflect that context

## RICE Scoring Formula
- **Reach** — How many users/processes impacted? (1-10)
- **Impact** — How significantly does it improve outcomes? (1-10)
- **Confidence** — How certain are we about estimates? (1-10)
- **Effort** — How much work is required? (1-10, higher = more effort)

## Tech Stack
- **UI:** Streamlit (Python)
- **AI:** Anthropic Claude API
- **Data:** Pandas
- **Deployment:** Streamlit Community Cloud

## Run Locally
```bash
pip install -r requirements.txt
# Add ANTHROPIC_API_KEY to .streamlit/secrets.toml
python -m streamlit run app.py
```

## About
Built by [Padmini Nagarajan](https://www.linkedin.com/in/padmini-nagarajan/),
Product Owner with 10+ years in data analytics and digital workflow transformation.
This project is part of my AI Product Owner portfolio.