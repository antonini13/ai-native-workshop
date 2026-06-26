---
task_id: spec/plano-de-build
processador: agente + aprovacao-humana
gate: humano
---

# Plano de Build

## Objetivo

Organizar o trabalho em ondas de entrega. Define o MVP — o mínimo que valida
a aposta de produto — e o que fica para iterações posteriores.

A principal decisão aqui não é técnica: é de produto. O conjunto da Onda 1
precisa ser capaz de resolver o problema core identificado no Research. Se não
for, o time vai construir e não vai saber se a aposta estava certa.

## Contexto

Leia `output/spec-01-user-stories.md`.

## Processador

Agente de IA, seguido de aprovação humana antes de exportar para o Linear.

## Passos

1. **Onda 1 (MVP)** — Liste as stories marcadas como MVP. Para cada uma,
   confirme em 1 linha por que ela é essencial para validar a aposta de
   produto e não apenas "bom de ter".

2. **Checagem de coerência** — Faça esta pergunta explicitamente: o conjunto
   da Onda 1, sozinho, é capaz de resolver o insight principal identificado
   no Research? Responda sim ou não, com justificativa. Se não, ajuste a
   Onda 1 antes de continuar.

3. **Onda 2+** — Liste o que foi deliberadamente deixado de fora, com uma
   linha de justificativa para cada item. "Fica para depois" sem justificativa
   não é plano — é adiamento sem critério.

4. **Estimativas** — Para cada story da Onda 1, estime o tamanho:
   - P: horas ou 1-2 dias
   - M: 3-5 dias
   - G: 1-2 semanas
   Se não tiver contexto técnico suficiente, estime conservadoramente e
   sinalize a incerteza.

5. **Dependências** — Identifique se alguma story precisa ser feita antes de
   outra para que funcione. Dependências viram ordem de implementação.

## Formato de output

**Escreva:** `output/spec-02-build-plan.md`

```
## Onda 1 — MVP

| Story | Título | Tamanho | Depende de | Por que é MVP |
|-------|--------|---------|------------|---------------|
| US-01 |        |         |            |               |

## Checagem de coerência
O conjunto da Onda 1 resolve o seguinte problema identificado no Research:
[declaração do problema]

Resolve? [Sim | Não] — [justificativa]

## Onda 2+

| Story | Título | Motivo do adiamento |
|-------|--------|---------------------|

## Notas de incerteza
[Estimativas com baixa confiança e por quê]
```

## Critérios de aceite

- [ ] Onda 1 está definida com justificativa para cada story
- [ ] Checagem de coerência foi feita explicitamente e tem resposta
- [ ] Onda 2+ tem justificativa de adiamento para cada item
- [ ] Estimativas estão registradas com incertezas sinalizadas

## Gate

Humano — apresente o plano ao usuário e aguarde aprovação explícita antes de
exportar para o Linear.

Diga: "Aqui está o plano de build. A Onda 1 faz sentido como MVP? Posso criar
as tasks no Linear?"

Não continue até receber confirmação.
