# Voice Customer Support — ElevenLabs

**Status:** Implemented and tested.  
**Stack:** ElevenLabs Agents Platform · Voice agents · Document knowledge bases · Conditional routing

## Business context

I implemented a voice-based store assistant that separates general product questions from stock inquiries. A main agent receives the conversation and directs it to a specialist with the relevant prompt and knowledge document.

## My implementation

- Created voice agents and configured their prompts, first messages, voices and language settings.
- Tested a general assistant and an airline assistant with information supplied in the prompt.
- Added product information and stock documents as knowledge sources.
- Built a main agent, a product-support specialist and a stock specialist.
- Configured prompt overrides and separate knowledge assignments.
- Added routing conditions for product questions and stock questions.
- Tested both routes in spoken Preview conversations.

## Architecture

| Component | Responsibility |
| --- | --- |
| Main agent | Receive the request and select the product or stock route |
| Product support | Answer general Apple product questions using the product-details document |
| Stock specialist | Answer availability questions using the stock document |

I configured distinct voices for the three roles. Each specialist received its own document, while the main agent handled the initial routing.

## Results

In the product conversation, I asked about the latest Apple Watch model and received an answer with models described in the configured product context. In a separate stock conversation, I asked which MacBook Pro models were available and received the MacBook Pro M4 entry from the stock document.

The specialist answered the original question after transfer. The product conversation terminated after the closing exchange.

The product and stock responses refer to the example data configured for these tests.

## Technical documentation

- [Agent configuration and routing](https://github.com/wagner-stoffel/n8n-lab/tree/main/projects/elevenlabs-voice-agent)
- [Execution record](https://github.com/wagner-stoffel/n8n-lab/blob/main/projects/elevenlabs-voice-agent/validation.md)

[Back to portfolio](../../README.md)
