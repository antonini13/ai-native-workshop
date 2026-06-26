# Plano de Build — Spec Stage 2

## Onda 1 — MVP

| Story | Título | Tamanho | Depende de | Por que é MVP |
|-------|--------|---------|------------|---------------|
| US-01 | Preencher narrativa como destaque | M (3–5 dias) | — | É o core da solução — inverter a hierarquia narrativa/dados é o insight central do Research. Sem isso, nada muda |
| US-03 | Salvar rascunho automaticamente | P (1–2 dias) | US-01 | Líderes preenchem ao longo da semana — sem autosave, o medo de perder conteúdo recria a fricção que mata a adoção |
| US-02 | Enviar relatório com narrativa + dados | M (3–5 dias) | US-01 | Sem envio, o formulário é um caderno particular. O produto só fecha o ciclo quando o gestor recebe |
| US-04 | Gestor recebe com narrativa em destaque | M (3–5 dias) | US-02 | A mudança de design para o gestor valida que o relatório chegou certo — sem isso não dá pra medir se a aposta funcionou |

**Estimativa total Onda 1:** 10–17 dias úteis (~2–3 semanas para 1 desenvolvedor full-stack)

---

## Checagem de coerência

O conjunto da Onda 1 resolve o seguinte problema identificado no Research:

> "Líderes de time não conseguem comunicar o contexto real do seu trabalho semanal porque o Kanvas posiciona dados automáticos como conteúdo principal do relatório e narrativa do time como detalhe secundário."

**Resolve? Sim.**

A Onda 1 inverte a hierarquia (US-01), garante que o trabalho não é perdido (US-03), envia com a estrutura correta (US-02) e o gestor recebe com narrativa em destaque (US-04). Esse conjunto fecha o ciclo completo: líder preenche com dignidade → relatório representa o trabalho → gestor lê informação real. Os três primeiros usuários que abandonaram (Rafael com email manual, Lucas com Slack, Bruno com WhatsApp) conseguiriam fazer dentro do Kanvas o que hoje fazem fora.

O que não resolve na Onda 1: o feedback loop do gestor para o líder. Esse era o Padrão 2 do Research (hipótese 3 no ranking). É real, mas é causa secundária — o abandono começa pela má representação, não pela falta de resposta. A Onda 1 para a sangria primeiro.

---

## Onda 2+

| Story | Título | Motivo do adiamento |
|-------|--------|---------------------|
| US-05 | Histórico de relatórios anteriores | Útil para consistência, mas o líder pode verificar relatórios anteriores por outras vias no MVP. Não impede a validação da aposta principal |
| — | Loop de feedback do gestor para o líder | O maior gerador de motivação a longo prazo (Padrão 2 do Research), mas requer mais design e não impede a validação do Onda 1. Entra após confirmar que o preenchimento voltou |
| — | Lembretes automáticos de preenchimento | Reduz esquecimentos, mas o Research mostrou que o problema não é esquecimento — é falta de formato adequado. Só faz sentido depois de resolver o formato |
| — | Campos customizáveis por time | Monday.com validou que liberdade total gera inconsistência. A estrutura fixa da Onda 1 é deliberada — customização entra se o Research da Onda 2 mostrar que a estrutura fixa é limitante |

---

## Notas de incerteza

- **US-01 (M):** A estimativa assume que o formulário atual pode ser reorganizado sem refatoração estrutural do modelo de dados. Se o schema de `report_configured` armazena campos em estrutura rígida (não extensível), pode ser G. Recomendo checar antes de começar.
- **US-04 (M):** Depende de como o email de relatório atual é gerado. Se é template hardcoded, ajustar para incluir narrativa é P. Se é gerado dinamicamente com lógica complexa, pode ser G. Sinalizar para o time técnico avaliar na reunião de planning.
- **US-03 (P):** Autosave com debounce é implementação padrão se o frontend já usa estado gerenciado (React/Vue). Se não, adicionar 1 dia de buffer.
