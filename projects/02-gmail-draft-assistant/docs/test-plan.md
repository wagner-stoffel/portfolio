# Gmail Draft Assistant — implementation record

I implemented and exercised a conversational workflow for retrieving email content and creating a Gmail draft.

| Component | Work performed |
| --- | --- |
| Chat interaction | Connected the chat trigger to the AI Agent |
| Model and memory | Connected the OpenAI chat model and Simple Memory |
| Email retrieval | Configured Gmail Message / Get Many with a relative received-after filter |
| Summary | Asked the agent to summarize the retrieved email content |
| Draft configuration | Configured Gmail Draft / Create with a fixed recipient and model-defined subject and text body |
| Draft creation | Requested a draft through the conversation and created it in Gmail |

[Back to case study](../README.md)
