# Equity Agent & Portfolio Rebalancer — agent instructions

I configured the agent's task instructions and tool descriptions for the portfolio-rebalancing workflow.

## Business objective and input

The form submission supplies the rebalancing request. I mapped this input into the agent prompt and described the objective for the portfolio update.

## Tool guidance

I configured instructions for reading the portfolio, retrieving EOD prices, updating matching ticker rows and writing proposed holdings to a separate quantity column.

The portfolio-reading tool description directs the agent to read the sheet before updates and read it again afterward to inspect the resulting allocation.

## Completion response

I configured the agent's completion response and used it in an If node to route the workflow to the corresponding notification.

I inspected executions and refined the prompt mapping, instructions and tool descriptions while testing successful and unsuccessful versions.

[Execution record](test-plan.md) · [Back to case study](../README.md)
