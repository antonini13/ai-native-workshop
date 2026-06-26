# Guia de Decomposição — Como transformar uma tarefa em contrato

## Passo 1 — Escolha o gargalo certo

Antes de decompor, escolha a tarefa certa. Um bom candidato tem:

| Critério | Pergunta |
|----------|----------|
| Repetição | Você faz isso toda semana / todo ciclo? |
| Volume | Há muitos inputs para processar (entrevistas, tickets, dados)? |
| Padronização | O resultado tem sempre a mesma estrutura? |
| Valor para decisão | O output alimenta uma decisão importante? |

**Exemplo no case Kanvas:** analisar 10 entrevistas individualmente, separar
sinais comportamentais de atitudinais, cruzar com dados quantitativos.
Repetitivo, alto volume, resultado estruturado, alimenta o diagnóstico.

---

## Passo 2 — Decomponha a tarefa

Antes de escrever o contrato, responda:

1. **O que precisa estar pronto antes de começar?**
   → vira o `## Contexto`

2. **Quais são os passos em ordem?**
   → vira o `## Passos`

3. **Quem ou o quê executa cada passo?**
   → vira o `## Processador`
   - Só LLM? → Agente de IA
   - Precisa de ferramenta externa (Lovable, Linear, API)? → Agente + ferramenta
   - Precisa de julgamento humano? → Gate humano

4. **Como é o resultado?**
   → vira o `## Formato de output`

5. **Como sei que está certo?**
   → vira os `## Critérios de aceite`

6. **O próximo passo pode começar automaticamente ou precisa de aprovação?**
   → vira o `## Gate`

---

## Passo 3 — Escreva o contrato

Use o arquivo `template-contrato-de-task.md` como base.
Preencha campo a campo seguindo as respostas do Passo 2.

---

## Exemplo real: `01-mapear-evidencias.md`

| Campo | Decisão tomada |
|-------|----------------|
| Objetivo | Inventário de evidências — separar comportamental de atitudinal, sem tirar conclusões ainda |
| Contexto | Ler o onboarding summary + 10 entrevistas + analytics + competitive |
| Processador | Agente de IA — tarefa de leitura e classificação, sem julgamento subjetivo |
| Passos | Processar uma fonte por vez: entrevistas → métricas → concorrentes → cruzamento → lacunas |
| Formato | Tabela de fontes + listas separadas de sinais comportamentais e atitudinais |
| Critérios | Todas as 10 entrevistas processadas, cada sinal com fonte, contradições sinalizadas |
| Gate | Automático — resultado é input da próxima task, não precisa de aprovação |
