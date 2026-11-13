# Voice Portfolio Assistant — ElevenLabs + n8n

**Status:** Implemented, tested and published; consecutive questions tested through the agent's shareable link.  
**Stack:** ElevenLabs · n8n · Google Gemini · Google Sheets

## Business context

I built a conversational voice interface for querying portfolio holdings stored in Google Sheets. ElevenLabs handles the voice conversation, while an n8n workflow retrieves portfolio data and returns the answer.

I also implemented an n8n-orchestrated audio pipeline to process a recorded question and return a generated audio response.

## Implemented workflows

### Audio request and response

I connected a browser recording page to an n8n POST webhook. The workflow transcribes the uploaded audio with ElevenLabs, passes the text to a Gemini-powered AI Agent, generates speech with ElevenLabs and returns the audio file to the browser.

I generated and played audio using two voices, then tested the complete pipeline with a spoken arithmetic question. The returned audio answered that two plus two is four.

### Conversational portfolio lookup

I created an ElevenLabs agent with a webhook tool that sends a portfolio question to n8n as a JSON `question` field. The n8n agent uses Gemini and a Google Sheets tool to retrieve holdings and return its answer.

I configured a 60-second tool timeout and speech before the lookup. I mapped the webhook's `body.question` field to the n8n agent prompt and returned the agent result through Respond to Webhook.

## Integration and debugging

I inspected failed executions and corrected three data mappings: the incoming binary audio property, the transcription field supplied to the agent, and the portfolio question received in the webhook body.

I verified the holdings lookup with a temporary chat trigger before connecting it to the voice agent.

## Publication and results

I published the n8n workflow and ElevenLabs agent, saved the production webhook URL in the voice-agent tool and tested the shared agent link.

The voice assistant returned two SPY shares for the configured portfolio. In the same conversation, it answered a follow-up question about the other holdings.

## Technical documentation

- [Workflow configuration and request mapping](https://github.com/wagner-stoffel/n8n-lab/tree/main/projects/elevenlabs-n8n-integration)
- [Execution record](https://github.com/wagner-stoffel/n8n-lab/blob/main/projects/elevenlabs-n8n-integration/validation.md)

[Back to portfolio](../../README.md)
