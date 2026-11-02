# Equity EOD AI Agent — test plan

This plan separates one **observed** successful execution from **unexecuted** acceptance scenarios.

## Observed smoke test

| Check | Evidence | Status |
| --- | --- | --- |
| Chat receives a natural-language question | Google end-of-day price prompt visible | Observed |
| AI Agent invokes an external data tool | Marketstack tool calls appear in the n8n log | Observed |
| Tool returns structured information | EOD fields including close and volume shown | Observed |
| Agent provides a readable response | GOOGL and GOOG closing prices shown | Observed |
| Execution duration | Approximately 6.88 seconds for one recorded run | Observed |

The screenshot demonstrates one successful execution, **not** an accuracy or performance benchmark. The returned prices were not independently verified.

## Planned acceptance tests

| ID | Scenario | Acceptance criterion | Status |
| --- | --- | --- | --- |
| T01 | Valid ticker | Return verified source, date, ticker, currency, and EOD close | Not run |
| T02 | Ambiguous company name | Clarify or explicitly distinguish share classes | Not run |
| T03 | Unknown ticker | No fabricated result; clear explanation | Not run |
| T04 | Missing market day | Report unavailable data, not an invented close | Not run |
| T05 | Provider timeout or rate limit | Useful and safe error handling | Not run |
| T06 | Follow-up question | Use session context without mixing assets | Not run |
| T07 | Data attribution | State historical EOD status and identify source | Not run |
| T08 | Credentials | No secrets in any exported or committed files | Not run |

## Criteria before production use

- Export, review, and sanitize the workflow JSON.
- Record model, node versions, API plan, and example inputs.
- Run the above tests and capture results.
- Add explicit tool error handling and date/currency validation.
- Check key management and upstream API usage limits.
