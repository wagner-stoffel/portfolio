# Equity EOD AI Agent & Portfolio Rebalancer

**Status:** Implemented and exercised as a learning project, including successful and unsuccessful runs.  
**Stack:** n8n · OpenAI API · Marketstack · Google Sheets · Gmail · Pushover

## Business context

I developed this project from an assistant that retrieves historical end-of-day (EOD) equity prices into a workflow that reads a portfolio, updates its prices, proposes rebalancing quantities and communicates the result.

The Day 5 exercises connected data retrieval, spreadsheet updates, agent instructions and conditional notifications into one business process. I completed the exercises, including successful and unsuccessful versions and the publication exercise.

## Implemented workflows

### EOD price assistant

A chat trigger passes a natural-language question to an AI Agent connected to a chat model, Simple Memory and a Marketstack tool. The agent retrieves EOD records and formats an answer. EOD closes are historical market data.

### Portfolio rebalancer — Day 5

A form submission supplies the rebalancing instruction to the AI Agent. The agent uses a chat model and tools to:

1. Read the portfolio from Google Sheets.
2. Retrieve the latest available EOD prices from Marketstack.
3. Update prices in the matching ticker rows.
4. Write proposed holdings to a separate new-quantity column.
5. Read the sheet again to check the resulting allocation and revise the proposal.
6. Send an email report and a Pushover notification.

An If node routes the final agent response to a success or failure notification. I also completed the exercise that publishes the workflow and triggers it through the production form URL.

The workflow produces a spreadsheet proposal and communicates decisions; it does not place orders with a broker.

## Configuration and learning

| Element | Work carried out |
| --- | --- |
| Form input | Mapped the submitted instruction into the agent prompt instead of relying on a chat-trigger field |
| Tool descriptions | Added portfolio-specific guidance, including rereading the sheet after updates |
| Sheets tools | Separated reading, price updates and proposed-quantity updates |
| Agent instructions | Described the business objective, tool sequence and completion response |
| Iterations | Explored the iteration setting as part of the rebalancing exercise |
| Conditional notifications | Used the agent output in an If node to select the notification branch |
| Execution inspection | Examined execution logs and tool interactions while iterating through successful and unsuccessful versions |
| Publication | Exercised the published workflow through its production form URL |

The form-driven workflow is a separate interaction from the conversational assistant: it receives a self-contained request rather than a chat history.

## Results and lessons

I completed the Day 5 exercises with both successful and unsuccessful executions. Working through those versions demonstrated how prompt mapping, tool descriptions and instructions influence whether the agent performs the business task.

The conditional notification checks the agent's completion response. That response is a workflow signal, not independent proof of mathematical correctness. The exercise also uses a reread of the sheet to inspect the allocation.

See the [execution record](docs/test-plan.md) and the [technical lab notes](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/portfolio-rebalancer).

## Demonstrated behavior

**Test prompt**

> Qual o end of day equity price for Google?

**Observed answer in the n8n chat** (for October 30, 2026):

| Symbol | EOD close returned by the workflow |
| --- | ---: |
| `GOOGL` | USD 279.84 |
| `GOOG` | USD 278.22 |

These values document **what the recorded workflow returned**; they have not been independently verified against an exchange or a second data provider. They are not live quotes.

The Marketstack tool's visible response included structured fields such as `open`, `high`, `low`, `close`, `volume`, and adjusted-price fields.

### Execution evidence

The successful n8n execution shown in the original test had:

- **Overall duration:** approximately 6.88 seconds.
- **Token usage shown in the log:** approximately 421 tokens.
- **Selected Marketstack tool call:** approximately 480 milliseconds.
- **Execution log:** repeated calls to the chat model, memory, and Marketstack tool.

These are observations from **one run**, not a performance benchmark or guarantee.


## Scope of the results

The Day 5 completion record reflects my execution of the course exercises, including the publication exercise. The original EOD measurements above belong only to that earlier run. They are not performance measurements of the rebalancer or evidence of continuous production operation.

**Tools:** [n8n](https://n8n.io/) · [OpenAI API](https://platform.openai.com/) · [Marketstack](https://marketstack.com/)
