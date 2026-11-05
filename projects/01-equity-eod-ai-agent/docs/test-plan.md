# Equity EOD AI Agent — test plan

I use this plan to separate my recorded successful execution from checks I still need to run.

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

## Context and tool checks — not run

Apply the [proposed system prompt](system-prompt.md) in a test workflow before testing its behavior. Record the actual model, node versions, memory settings, and tool configuration used. I will record outcomes from my own test runs.

| ID | Scenario and input | Acceptance criterion | Status |
| --- | --- | --- | --- |
| T09 | In the same chat session: "Meu nome é Ana." then "Qual é o meu nome?" | Answer Ana; the inspected model context contains the relevant previous exchange | Not run |
| T10 | Ask "Qual foi o último fechamento disponível de GOOGL?" | Concise Portuguese answer; explicitly identifies EOD data, source, date, ticker, close, and currency when supplied; flags missing fields | Not run |
| T11 | Start with "Olá", then request the latest available GOOGL close | Greeting does not trigger a market lookup; price request does; inspect the actual tool calls | Not run |
| T12 | Request the latest available GOOGL close | Tool input uses GOOGL; model-defined ticker input and Latest = Yes are confirmed in the node configuration | Not run |
| T13 | Compare the price answer with the structured Marketstack response | Ticker, market date, close, and available currency match the returned record; no invented values or real-time claim | Not run |

### Recording results

For each test, record the ID, input, expected behavior, observed result, and pass/fail status. Include a redacted execution excerpt or screenshot when available. For T09, keep both messages in the same session; start a fresh chat for independent scenarios where earlier context could influence the result.

Inspect the system message, relevant history, tool request, and tool response in the execution details. Distinguish node configuration from invocation arguments: a fixed Latest setting may be visible in the node rather than in model-generated arguments.

Keep unexecuted tests marked **Not run**. Record duration and token usage only when observed; one successful run does not demonstrate repeatability or a performance improvement.

## Sheets integration checks — not run

Use a separate synthetic sheet with unique symbols and known quantities. Record initial values, actual node/model versions, configured document and sheet, execution inputs/outputs, final cell values, and pass/fail results. Never publish account identifiers or real holdings.

| ID | Scenario | Acceptance criterion | Status |
| --- | --- | --- | --- |
| T14 | Read the selected test sheet | Returned rows and ticker/quantity/price fields match the selected document and tab | Not run |
| T15 | Update three distinct valid symbols | Each updated price equals its matching API EOD close; market dates and available currencies are recorded; no live-price claim | Not run |
| T16 | Preserve fields and row count | Quantities, tickers, unrelated columns, and row count remain unchanged; quantity is excluded from update mapping | Not run |
| T17 | Invalid symbol or empty API result | Affected price remains unchanged; failure is explicit; no invented value | Not run |
| T18 | Duplicate ticker or ambiguous company name | Ambiguity is reported before any affected row is updated | Not run |
| T19 | API timeout, revoked Sheets access, or partial failure | No false all-success claim; successful and failed rows are distinguished; failed writes are not reported as complete | Not run |
| T20 | Repeat request and inspect trace | No appended duplicate rows; inspect actual tool calls and compare each write with its source record; changed prices require corresponding source data | Not run |

I still need to implement and validate the proposed extension, including duplicate and failure handling.

## Criteria before production use

- Export, review, and sanitize the workflow JSON.
- Record model, node versions, API plan, and example inputs.
- Run the above tests and capture results.
- Add explicit tool error handling and date/currency validation.
- Check key management and upstream API usage limits.
