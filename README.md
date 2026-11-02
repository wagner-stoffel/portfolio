# Wagner Stoffel — AI Automation & Business Process Improvement

A professional portfolio combining **financial operations, business analysis, and hands-on AI automation**. This repository hosts a lightweight website and technical project case studies.

**Links:** [GitHub](https://github.com/wagner-stoffel) · [LinkedIn](https://www.linkedin.com/in/wagnerstoffel)

## Site

- [Home](index.html): professional focus and featured project.
- [About](about.html): background, expertise, and qualifications.
- [Projects](projects.html): documented technical work.
- [Contact](contact.html): verified professional contact links.

## Technical projects

| Project | Stack | Status |
| --- | --- | --- |
| [Equity EOD AI Agent](projects/01-equity-eod-ai-agent/README.md) | n8n, OpenAI API, Marketstack | Tested learning prototype |

The first project demonstrates an n8n agent with an OpenAI chat model, Simple Memory, and a tool for retrieving end-of-day equity prices. Its [test plan](projects/01-equity-eod-ai-agent/docs/test-plan.md) distinguishes what was observed from what remains to be tested.

## Preview locally

This site uses plain HTML and CSS, without a build process.

```bash
python -m http.server 8000
```

Visit `http://localhost:8000`. A GitHub Pages deployment is possible; do not assume it is enabled just because this repository is public.

## Repository structure

```text
portfolio/
├── index.html
├── about.html
├── projects.html
├── contact.html
├── assets/css/styles.css
├── projects/01-equity-eod-ai-agent/
│   ├── README.md
│   └── docs/test-plan.md
└── archive/alura-frontend/
```

The original Alura HTML/CSS exercise is preserved under [archive/alura-frontend](archive/alura-frontend/). It is not presented as the professional website.

## Principles

Each case study covers the problem, architecture, observed output, limits, and planned improvements. Learning projects are described as learning projects, not as client or production deliveries.

**Security:** Do not commit API credentials, secrets, or unreviewed n8n workflow exports. Credentials belong in the appropriate service's secret manager.
