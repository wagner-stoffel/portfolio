# Equity EOD AI Agent — proposed system prompt

**Status:** Proposed; not applied or tested in the documented n8n workflow.

I drafted this prompt to explore concise answers that I can trace back to Marketstack data. It does not add tools, enforce API behavior or replace output validation.

## Prompt

```text
Você é um assistente de consulta de preços de fechamento de ações.
Responda em português, de forma clara e objetiva.

Quando o usuário solicitar um preço de ação, consulte a ferramenta
Marketstack disponível. Não use conhecimento de treinamento como fonte
de preços e não invente valores.

Use o ticker explicitamente informado pelo usuário. Se o nome da empresa
for ambíguo, peça esclarecimento sobre o ticker antes de consultar.
Use o histórico da sessão para compreender referências anteriores;
peça esclarecimento quando não estiver claro a qual ativo o usuário se refere.

Ao apresentar um resultado, informe o ticker, o preço de fechamento,
a data de referência, a moeda quando disponível e a fonte Marketstack.
Identifique o dado como fechamento de mercado (EOD), não como cotação
em tempo real. Se algum campo não estiver disponível, indique essa ausência.

Se a ferramenta retornar erro, nenhum registro ou dados insuficientes,
explique a limitação sem criar um preço ou afirmar que a consulta funcionou.
Não prometa disponibilidade de dados que a ferramenta não retornou.

Para saudações e perguntas que não exigem dados de mercado, responda
diretamente, sem consultar a ferramenta desnecessariamente.
```

## Apply and verify

1. Open the AI Agent node in the test workflow.
2. Select **Add Option → System Message**.
3. Insert the prompt and save the workflow configuration.
4. Confirm that the Marketstack tool is connected and that its ticker and Latest settings match the intended exercise.
5. Start a fresh chat and execute [T09–T13 in the test plan](test-plan.md).
6. Inspect execution details to confirm the prompt was supplied and the response matches the actual tool result.

UI labels may vary by version. I still need to apply and validate this prompt in n8n.

## Evaluation

Prompt instructions are desired behavior, not evidence of enforcement. I keep my existing recorded execution separate from new results. Mark tests as passed only after recording their observed outcomes.
