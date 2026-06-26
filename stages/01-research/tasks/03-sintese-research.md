---
task_id: research/sintese
processador: agente + aprovacao-humana
gate: humano
---

# Síntese de Research

## Objetivo

Transformar padrões e hipóteses em um diagnóstico claro e uma pergunta de design
para o Shape. Este é o output principal do Research — ele alimenta todo o Stage 2.

O diagnóstico precisa ser honesto sobre o que sabe e o que não sabe. Um diagnóstico
que esconde incerteza é perigoso: o Shape vai construir sobre uma base falsa.

## Contexto

Leia `output/research-01-evidence-map.md` e `output/research-02-patterns.md`.

## Processador

Agente de IA, seguido de aprovação humana antes de continuar para o Shape.

## Passos

1. **Declaração do problema** — Escreva em 1 frase usando este template:
   "O problema é que [quem específico] [não consegue fazer o quê específico]
   [porque o quê específico]."
   Teste a frase: ela poderia se aplicar a qualquer produto? Se sim, está
   genérica demais. Refaça.

2. **Hierarquia de evidências** — Liste as 3 evidências mais fortes que sustentam
   o diagnóstico. Cada uma deve: citar a fonte, citar dado ou trecho específico,
   e explicar em 1 linha por que sustenta a declaração do problema.

3. **Insight principal** — O que o Research revelou que não era óbvio no
   onboarding? O que muda no entendimento do problema depois de analisar os
   dados? Este é o "aha" do processo — se não houver nada surpreendente, o
   Research foi raso.

4. **O que ainda não sabemos** — Registre honestamente as lacunas que permanecem.
   Para cada lacuna, indique o impacto na confiança do diagnóstico.

5. **Pergunta de design** — Formule a pergunta central para o Shape usando o
   template: "Como poderíamos [verbo de ação] para que [resultado para o usuário]?"
   A pergunta deve orientar o Shape sem ditar a solução.

Após concluir os 5 passos, escreva `output/01-research-summary.md` com o
conteúdo formatado de forma limpa.

## Formato de output

**Escreva:** `output/01-research-summary.md`

```
## Declaração do problema
[1 frase específica com quem, o quê e por quê]

## Top 3 evidências
1. [evidência] — fonte: [referência] — por que sustenta: [1 linha]
2. [evidência] — fonte: [referência] — por que sustenta: [1 linha]
3. [evidência] — fonte: [referência] — por que sustenta: [1 linha]

## Insight principal
[O que ficou claro que não era óbvio antes do Research]

## O que ainda não sabemos
- [lacuna] — impacto na confiança: [alto | médio | baixo]

## Pergunta de design para o Shape
Como poderíamos [verbo] para que [resultado]?
```

## Critérios de aceite

- [ ] Declaração do problema é específica — tem quem, o quê e por quê
- [ ] Cada evidência cita fonte e explica a relação com o diagnóstico
- [ ] Insight principal vai além da hipótese inicial do onboarding
- [ ] Lacunas estão registradas honestamente com impacto estimado
- [ ] Pergunta de design orienta o Shape sem ditar a solução

## Gate

Humano — apresente o summary ao usuário e aguarde aprovação explícita antes
de continuar para o Shape.

Diga: "Aqui está o diagnóstico do Research. Este problema faz sentido pra
você? Posso continuar para o Shape?"

Não continue até receber confirmação.
