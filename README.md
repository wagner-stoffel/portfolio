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

### [Equity EOD AI Agent & Portfolio Rebalancer](projects/01-equity-eod-ai-agent/README.md)

**Stack:** n8n · OpenAI API · Marketstack · Google Sheets · Gmail · Pushover  
**Status:** Implemented and tested, with successful and unsuccessful executions.

I developed an EOD price assistant into a form-driven portfolio-rebalancing workflow. It reads positions, updates prices, writes proposed quantities, checks the allocation and communicates through email and push notifications. I implemented conditional logic, inspected executions and published the workflow.

The [case study](projects/01-equity-eod-ai-agent/README.md) and [execution record](projects/01-equity-eod-ai-agent/docs/test-plan.md) describe the completed work.

## Field lab

I use [n8n-lab](https://github.com/wagner-stoffel/n8n-lab) to explore integrations, inspect data flows and document implemented workflows.

In my [messaging experiments](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/messaging), I built Pushover notifications, Telegram conversations and a Slack bot. The lab documents the integration setup and implementation details.

I keep selected cases here and smaller experiments in the lab. The [portfolio rebalancer](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/portfolio-rebalancer) combines portfolio updates with Gmail and Pushover notifications.

## How I approach delivery

**Discover → Define → Plan → Implement → Validate → Improve.** Business context and verification come before claims of success.

- [Delivery method](docs/delivery-method.md): approach to scope, process analysis, delivery, risks, and validation.
- [Case study template](docs/case-study-template.md): repeatable standard for future evidence-based documentation.

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
    └── 02-gmail-draft-assistant/
        ├── README.md
        └── docs/test-plan.md
```

## Standards

- Document the problem, objectives, scope, architecture, observed tests, limitations, and improvements.
- Distinguish completed, observed, planned, and untested work.
- Reference relevant technical documentation and respect third-party licenses.
- Do not publish credentials, personal information, or unreviewed workflow exports.
- Do not claim production use, measured impact, or repeatability without supporting evidence.
