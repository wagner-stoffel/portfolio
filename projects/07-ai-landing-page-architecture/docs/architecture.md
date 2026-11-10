# Dental campaign landing page — architecture specification

**Exercise:** Clínica Sonría, Workana, 10 November 2026.  
**Scope:** Solution design and AI coding direction; production deployment was not verified.

## User-facing requirements

- Campaign: teeth whitening, **20% off the first session**.
- Language: Spanish.
- Form: full name, phone number, email, preferred branch and message.
- Explicit, informed data-processing consent before submitting.
- A clear success or failure response, including loading and validation states.

## Logical architecture

```text
Public visitor
    |
    v
Vercel — React / Tailwind landing page
    |  validated form + consent + anti-spam token
    v
Supabase Edge Function
    |-- verify inputs and Cloudflare Turnstile
    |-- write to Supabase PostgreSQL
    |-- notify reception through Resend
    v
Submission acknowledgement

Reception staff
    |
    v
Supabase Auth -> Protected reception view
    |
    v
Authorised records under Row Level Security
```

## Security model

- Never expose service-role keys, Resend credentials or other secrets in frontend code.
- Use secure server-side environment variables for credentials.
- Apply Row Level Security and least privilege so anonymous visitors cannot list or read submissions.
- Authenticate and authorise reception users before displaying any lead records.
- Validate fields on the server, not only in the browser.
- Verify anti-bot tokens server-side; rate-limit abusive traffic.
- Avoid including unnecessary sensitive patient data in notification emails.
- Keep an explicit link to the clinic's privacy notice and store the consent decision appropriately.
- Apply a retention and deletion policy before a real deployment.

## Implementation prompt provided to the AI assistant

> Build a responsive Spanish-language teeth-whitening campaign landing page with a 20% discount on the first session. Use React and Tailwind CSS for the frontend, Vercel for hosting, Supabase PostgreSQL for storage, Supabase Auth for reception access, and Supabase Edge Functions for backend processing. Create a lead form with name, phone, email, branch and message; require explicit privacy consent and Cloudflare Turnstile validation. Notify reception through Resend. Keep secrets server-side, restrict database access with Row Level Security, and build a protected reception dashboard. Implement accessible mobile-first layouts, validation, loading states and success/error feedback. Keep the specified stack.

## Verification boundary

The exercise was submitted, but no code snapshot, public site URL, database migration, email-delivery log or dashboard test was available for verification. This artefact documents the design and implementation brief rather than a proven production launch.
