# Product Expert Voice Agent — Agentic RAG

**Status:** Implemented, tested and published.  
**Stack:** ElevenLabs · n8n · Supabase · Google Gemini · OpenAI embeddings

## Business context

I built a voice sales assistant that answers computer-accessory questions using a product catalog stored in Supabase. The solution combines my product-ingestion workflow with agent-directed retrieval and spoken responses.

## Architecture

| Component | My implementation |
| --- | --- |
| Knowledge base | 60 product documents with category metadata and 1536-dimensional embeddings |
| Retrieval | Supabase Vector Store exposed as an n8n AI Agent tool, with a 10-document limit |
| Question answering | Google Gemini uses retrieved product text to compose the answer |
| Voice interface | ElevenLabs sales agent |
| Integration | POST webhook carrying a required question string; JSON response from n8n |

I configured the query embedding model to match the model used during ingestion. I mapped the webhook's question field to the agent input and used Respond to Webhook to return the answer.

## Implementation and testing

I first tested retrieval in chat with Simple Memory. Questions about keyboards and computer-memory pricing produced answers based on the product knowledge base.

I then connected the ElevenLabs agent to the webhook backend and removed the backend's chat memory. In a spoken keyboard test, the agent acknowledged the lookup, described product categories, named catalog options and asked about the customer's intended use.

I inspected the completed n8n execution, including the retrieval tool and its returned documents.

## Publication and telephone configuration

I published the n8n workflow and ElevenLabs agent, saved the production webhook URL in the voice tool and opened the shareable agent link.

I also configured the Twilio number-import form in ElevenLabs using the phone number and Twilio account credentials.

## Technical documentation

- [Product ingestion](../08-product-knowledge-ingestion/README.md)
- [Retrieval and voice configuration](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/product-expert-voice-agent)
- [Execution record](https://github.com/wagner-stoffel/n8n-lab/blob/main/experiments/product-expert-voice-agent/validation.md)

[Back to portfolio](../../README.md)
