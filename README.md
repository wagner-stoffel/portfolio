# Wagner Stoffel | Project Management, AI & Automation

A professional portfolio connecting **project delivery, business analysis, artificial intelligence, and workflow automation**. It is grounded in experience in financial operations, administration, consulting, and continuous improvement.

**Profiles:** [LinkedIn](https://www.linkedin.com/in/wagnerstoffel) · [GitHub](https://github.com/wagner-stoffel)

## Professional focus

| Area | Focus |
| --- | --- |
| Project management | Objectives, requirements, planning, prioritization, stakeholder communication, risks, and delivery. |
| Business analysis | AS-IS and TO-BE processes, pain points, solution evaluation, and measurable outcomes. |
| Artificial intelligence | LLMs, AI agents, tool integration, and evidence-based validation. |
| Workflow automation | n8n, APIs, systems integration, and operational improvement. |

## Selected project

### [Equity EOD AI Agent](projects/01-equity-eod-ai-agent/README.md)

**Stack:** n8n · OpenAI API · Marketstack  
**Status:** Tested learning prototype — one recorded successful run, **not** a production deployment.

The assistant retrieves historical end-of-day equity data through an external API tool. Its case study includes architecture, implementation notes, observed behavior, limitations, and a [test plan](projects/01-equity-eod-ai-agent/docs/test-plan.md). Reported API values have not been independently verified.

## How I approach delivery

**Discover → Define → Plan → Implement → Validate → Improve.** Business context and verification come before claims of success.

- [Delivery method](docs/delivery-method.md): approach to scope, process analysis, delivery, risks, and validation.
- [Case study template](docs/case-study-template.md): repeatable standard for future evidence-based documentation.

Planned areas for future documented projects include business-process automation, AI-assisted knowledge retrieval, and project-delivery artifacts. They are **not** presented as completed work.

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
    └── 01-equity-eod-ai-agent/
        ├── README.md
        └── docs/test-plan.md
```

## Standards

- Document the problem, objectives, scope, architecture, observed tests, limitations, and improvements.
- Distinguish completed, observed, planned, and untested work.
- Credit courses and third-party sources without presenting teaching materials as original.
- Do not publish credentials, personal information, or unreviewed workflow exports.
- Do not claim production use, measured impact, or repeatability without supporting evidence.
