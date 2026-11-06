# Equity Agent & Portfolio Rebalancer — execution record

## Day 5 exercises

I completed the Day 5 exercises, including both successful and unsuccessful versions. This record summarizes the scope of that practical work.

| Exercise area | Work completed |
| --- | --- |
| Form trigger | Received the rebalancing request and mapped the form field to the agent prompt |
| Google Sheets | Read portfolio positions and used separate updates for prices and proposed quantities |
| Marketstack | Connected EOD data retrieval to the portfolio workflow |
| Agent context | Worked with task instructions and tool descriptions |
| Rebalancing | Updated proposed holdings and reread the sheet to check the allocation |
| Communication | Integrated Gmail reports and Pushover notifications |
| Conditional logic | Built the If-based routing for the agent's completion response |
| Debugging | Executed successful and unsuccessful versions and inspected execution details |
| Publication | Completed the published-form workflow exercise |

This is a qualitative record of completed exercises. It does not assign individual pass/fail results or performance measurements to runs beyond the information recorded here.

## Earlier EOD smoke test

| Check | Recorded observation |
| --- | --- |
| Natural-language input | Google end-of-day price question |
| External tool use | Marketstack calls visible in the n8n log |
| Structured response | EOD fields including close and volume |
| Agent answer | GOOGL and GOOG closing prices |
| Duration | Approximately 6.88 seconds for the original run |
| Token usage | Approximately 421 tokens for the original run |

The returned prices document the workflow output and were not independently verified. These measurements describe the earlier EOD lookup, not the Day 5 rebalancer.

[Back to case study](../README.md)
