# Gmail Draft Assistant — n8n + OpenAI + Gmail

**Status:** Implemented and tested.  
**Stack:** n8n · OpenAI · Gmail · Simple Memory

## Business context

I built a chat-driven assistant that retrieves recent emails, summarizes the returned content and creates a draft from a conversational request.

## Implementation

| Component | Configuration |
| --- | --- |
| Chat trigger | Receives the user's request |
| AI Agent and OpenAI chat model | Interpret the request and use the connected Gmail tools |
| Simple Memory | Maintains context within the conversation |
| Gmail Message / Get Many | Retrieves messages using a relative received-after filter |
| Gmail Draft / Create | Creates a text draft with model-defined subject and body and a configured recipient |

I configured the received-after boundary with a relative date expression for the preceding day. I connected the Gmail tools to the agent and used a fixed recipient for draft creation.

## Executed flow

Chat request → Gmail retrieval → summary → draft request → Gmail draft creation.

I requested a summary of retrieved email content and then asked the agent to prepare a draft. The workflow created the draft in Gmail.

## Execution record

The [implementation record](docs/test-plan.md) documents the configured components and exercised flow.

[Back to portfolio](../../README.md)
