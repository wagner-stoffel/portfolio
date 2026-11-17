# AI Web Search Pipeline

**Status:** Implemented and tested.  
**Stack:** n8n · OpenRouter · DeepSeek V3.2 · Structured Output Parser · Firecrawl · HTTP Request

## Business context

I built a workflow that turns a natural-language research question into a structured web query and delivers the retrieved results to an external endpoint. The implementation connects conversational input, model output validation, web search and HTTP integration.

## Implementation

```text
Question → Structured search query → Web search → JSON delivery
```

I configured an AI Agent with OpenRouter, DeepSeek V3.2 and Simple Memory. I added a Structured Output Parser defining a search_query string, then mapped that field into Firecrawl's search operation.

I connected the returned data to an HTTP Request node using POST and a JSON body. I used Webhook.site to inspect the receiving side.

## Execution results

I tested a question about which LLMs to use in 2026. The agent returned the structured query, Firecrawl returned URLs, titles and descriptions, and the receiving endpoint displayed the POST payload. I inspected the successful workflow execution.

These results demonstrate structured query generation, search integration and delivery of the returned data.

## Related integration

I also implemented and published a Google Drive folder-monitoring workflow. It polls for file creation and sends a Pushover notification. Creating a copy of a file triggered a successful execution and delivered the notification.

- [Search implementation](https://github.com/wagner-stoffel/n8n-lab/tree/main/projects/ai-web-search-pipeline)
- [Search execution record](https://github.com/wagner-stoffel/n8n-lab/blob/main/projects/ai-web-search-pipeline/validation.md)
- [Drive notifications](https://github.com/wagner-stoffel/n8n-lab/tree/main/projects/google-drive-file-notifications)
- [Back to portfolio](../../README.md)
