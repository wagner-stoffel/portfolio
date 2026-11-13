# Wagner Stoffel | Project Management, AI & Automation

I connect **project delivery, business analysis, artificial intelligence, and workflow automation**. My work is grounded in experience in financial operations, administration, consulting, and continuous improvement.

**Profiles:** [LinkedIn](https://www.linkedin.com/in/wagnerstoffel) · [GitHub](https://github.com/wagner-stoffel)

## Professional focus

| Area | Focus |
| --- | --- |
| Project management | Objectives, requirements, planning, prioritization, stakeholder communication, risks, and delivery. |
| Business analysis | AS-IS and TO-BE processes, pain points, solution evaluation, and measurable outcomes. |
| Artificial intelligence | LLMs, AI agents, tool integration, and evidence-based validation. |
| Workflow automation | n8n, APIs, systems integration, and operational improvement. |

## Selected cases

### [Product Knowledge Ingestion](projects/08-product-knowledge-ingestion/README.md)

**Stack:** n8n · Google Sheets · Supabase · PostgreSQL/pgvector · OpenAI embeddings  
**Status:** Implemented and tested.

I built a product-data ingestion pipeline that transforms 60 catalog rows into readable documents, generates 1536-dimensional embeddings and stores them with category metadata in Supabase. I inspected the results, corrected a formatting issue and reloaded the 60 documents.

### [AI-Directed Landing Page — Dental Whitening Campaign](projects/07-ai-landing-page-architecture/README.md)

**Design stack:** React · Tailwind CSS · Vercel · Supabase · Resend · Cloudflare Turnstile  
**Status:** Architecture and AI implementation brief completed; exercise submitted. Production deployment not verified.

I specified the architecture and AI coding brief for a Spanish-language campaign page offering 20% off a first whitening session. The design covers a lead form, reception dashboard, authenticated access, server-side secrets, consent, anti-spam checks and new-lead notification.

### [Appointment Confirmation Workflow — CRM & Calendar Automation](projects/06-booking-confirmation-workflow/README.md)

**Tools:** Kommo · Google Calendar · Meta WhatsApp Business · Gmail · Website forms  
**Status:** Partially implemented and tested in a simulator; the last captured free-slot branch was not connected.

I designed the booking process as a conditional workflow and configured its initial CRM lookup, new-contact creation and branch-specific availability checks. The recorded sample execution passed those steps and stopped at an unconnected output. The case study distinguishes tested nodes from the intended booking and confirmation path.

### [Dental WhatsApp AI Assistant — Policy Resolution & Safety Testing](projects/05-whatsapp-dental-assistant/README.md)

**Focus:** Conversational AI · System prompts · Safety boundaries · Human handoff  
**Status:** Completed simulator exercise; five patient scenarios tested successfully. No production deployment.

I reconciled six conflicting operational sources into a WhatsApp assistant's instructions for a dental clinic. I defined booking-request boundaries, emergency escalation and clinical safety rules, tested five patient scenarios and refined two responses after reviewing the results.

### [Voice Portfolio Assistant](projects/04-voice-portfolio-assistant/README.md)

**Stack:** ElevenLabs · n8n · Google Gemini · Google Sheets  
**Status:** Implemented, tested and published.

I connected an ElevenLabs voice agent to an n8n portfolio-query workflow through a POST webhook. I published both sides and tested consecutive holdings questions through the agent's shareable link. I also built and tested an audio transcription, agent-response and speech-generation pipeline orchestrated by n8n.

### [Voice Customer Support](projects/03-voice-customer-support/README.md)

**Stack:** ElevenLabs Agents Platform · Voice agents · Knowledge bases · Conditional routing  
**Status:** Implemented and tested.

I built a main voice agent and separate product and stock specialists. I configured prompts, voices, knowledge documents and routing conditions, then tested both paths in spoken conversations.

### [Gmail Draft Assistant](projects/02-gmail-draft-assistant/README.md)

**Stack:** n8n · OpenAI · Gmail · Simple Memory  
**Status:** Implemented and tested.

I connected email retrieval and draft creation to a conversational agent. I configured a relative date filter, summarized retrieved email content and created a draft in Gmail.

### [Equity EOD AI Agent & Portfolio Rebalancer](projects/01-equity-eod-ai-agent/README.md)

**Stack:** n8n · OpenAI API · Marketstack · Google Sheets · Gmail · Pushover  
**Status:** Implemented and tested, with successful and unsuccessful executions.

I developed an EOD price assistant into a form-driven portfolio-rebalancing workflow. It reads positions, updates prices, writes proposed quantities, checks the allocation and communicates through email and push notifications. I implemented conditional logic, inspected executions and published the workflow.

The [case study](projects/01-equity-eod-ai-agent/README.md) and [execution record](projects/01-equity-eod-ai-agent/docs/test-plan.md) describe the completed work.

## Field lab

I use [n8n-lab](https://github.com/wagner-stoffel/n8n-lab) to explore integrations, inspect data flows and document implemented workflows.

In my [messaging experiments](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/messaging), I built Pushover notifications, Telegram conversations and a Slack bot. The lab documents the integration setup and implementation details.

I keep selected cases here and smaller experiments in the lab. The [portfolio rebalancer](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/portfolio-rebalancer) combines portfolio updates with Gmail and Pushover notifications.

I documented my [analysis of retrieval, embeddings and agentic RAG](https://github.com/wagner-stoffel/n8n-lab/blob/main/docs/retrieval-and-agentic-rag.md), alongside my [Supabase account setup and platform review](https://github.com/wagner-stoffel/n8n-lab/blob/main/docs/supabase-setup.md).

## How I approach delivery

**Discover → Define → Plan → Implement → Validate → Improve.** Business context and verification come before claims of success.

- [Delivery method](docs/delivery-method.md): approach to scope, process analysis, delivery, risks, and validation.
- [Case study template](docs/case-study-template.md): structure for documenting completed implementations and observed results.

## Portfolio website

- [Home](index.html) — current professional focus
- [About](about.html) — experience and qualifications
- [Projects](projects.html) — documented projects
- [Contact](contact.html) — professional links

The website is an independent, lightweight HTML/CSS implementation. Preview locally with `python -m http.server 8000`, then open `http://localhost:8000`.

## Repository structure

```text
portfolio/
├── README.md
├── index.html
├── about.html
├── projects.html
├── contact.html
├── assets/css/styles.css
├── docs/
│   ├── delivery-method.md
│   └── case-study-template.md
└── projects/
    ├── 01-equity-eod-ai-agent/
    │   ├── README.md
    │   └── docs/
    │       ├── system-prompt.md
    │       └── test-plan.md
    ├── 02-gmail-draft-assistant/
    │   ├── README.md
    │   └── docs/test-plan.md
    ├── 03-voice-customer-support/
    │   └── README.md
    ├── 04-voice-portfolio-assistant/
    │   └── README.md
    ├── 05-whatsapp-dental-assistant/
    │   ├── README.md
    │   └── docs/assistant-specification.md
    ├── 06-booking-confirmation-workflow/
    │   ├── README.md
    │   └── docs/workflow-design.md
    ├── 07-ai-landing-page-architecture/
    │   ├── README.md
    │   └── docs/architecture.md
    └── 08-product-knowledge-ingestion/
        └── README.md
```
