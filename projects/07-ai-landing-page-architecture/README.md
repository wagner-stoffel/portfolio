# AI-Directed Landing Page — Dental Whitening Campaign

**Status:** Architecture and AI implementation brief completed and the Workana exercise submitted; a deployed site, generated code and functioning backend were not independently verified.  
**Role:** Solution architecture, service selection, security requirements and AI development direction.  
**Context:** Clínica Sonría — Workana technical exercise, 10 November 2026.  
**Proposed stack:** React · Tailwind CSS · Vercel · Supabase · Resend · Cloudflare Turnstile

## Business challenge

The clinic proposed a new teeth-whitening campaign with **20% off the first session** and needed a Spanish-language landing page to collect inquiries. Reception needed a protected place to review submissions and to receive a notice whenever a new lead arrived. Because submissions contain patient contact details, access control, spam mitigation and explicit consent were part of the requirements.

## Architecture specified

I designed a separation between the public campaign interface, server-side submission handling and a protected reception view.

| Concern | Architecture choice |
| --- | --- |
| Public frontend | React + Tailwind CSS |
| Hosting | Vercel |
| Backend processing | Supabase Edge Functions |
| Persistent storage | Supabase PostgreSQL |
| Reception authentication | Supabase Auth; authorised reception staff only |
| Notifications | Resend email to the reception mailbox |
| Secrets | Server-side environment variables; never exposed to the browser |
| Database permissions | Backend-controlled writes and Row Level Security |
| Spam mitigation | Cloudflare Turnstile |
| Patient consent | Explicit required consent checkbox and privacy notice |

The public form requests name, phone, email, branch and message. The server-side process validates input, verifies anti-spam protection, persists the record and sends a notification. The reception dashboard requires authentication before reading any lead data.

## AI implementation direction

I directed the coding assistant to work with the selected technologies rather than invent a new stack. The brief required:

- A responsive, accessible, Spanish-language campaign page with clear 20% offer messaging.
- A form covering the five specified fields and explicit consent.
- Input validation, submission states and confirmation/error feedback.
- Secure backend submission handling and database access controls.
- An authenticated reception dashboard and new-submission email notifications.
- Server-only API credentials and safeguards against public access to records.

The architecture exercise was submitted. No independent evidence of a live deployment, working Supabase database, delivered Resend messages or completed dashboard tests was captured.

## Technical artefact

- [Architecture and implementation brief](docs/architecture.md)

## What this demonstrates

I translated a business brief into an explicit architecture, selected individual platform responsibilities and provided an AI coding agent with concrete technical and privacy constraints. The exercise emphasised decision-making, service boundaries and safe handling of patient information.

[Back to portfolio](../../README.md)
