---
task_id: shape/enquadrar-oportunidade
processador: agente
gate: automatico
---

# Enquadrar a Oportunidade

## Objetivo

Definir com precisão quem sofre com o problema, em qual momento específico dói,
e qual é o valor de resolver isso. Antes de explorar soluções, precisamos
entender exatamente o que estamos resolvendo — e para quem.

"Melhorar a experiência dos usuários" não é uma oportunidade. "Permitir que
líderes de time adicionem contexto antes que o relatório chegue ao gestor" é
uma oportunidade.

## Contexto

Leia `output/01-research-summary.md`.

## Processador

Agente de IA

## Passos

1. **Usuário mais afetado** — Identifique quem sente a dor mais diretamente.
   Descreva em 2-3 características de comportamento e contexto. Cargo sozinho
   não é suficiente: "líder de time que precisa reportar progresso para um gestor
   que não acompanha o dia a dia" é mais útil que "tech lead".

2. **Momento específico** — Em qual situação exata o problema aparece?
   Use o formato: "quando [X acontece], [Y fica impossível ou custoso]."
   Se o problema aparece em múltiplos momentos, identifique o mais crítico.

3. **Custo atual** — O que o usuário faz hoje para contornar o problema?
   Descreva o workaround, o esforço envolvido, e o que é perdido no processo
   (tempo, qualidade da informação, confiança, relacionamento).

4. **Valor de resolver** — Se o problema fosse resolvido, o que mudaria
   concretamente para o usuário? E para o negócio? Seja específico.

5. **Declaração de oportunidade** — Escreva em 1 parágrafo integrando os
   pontos anteriores: quem, o problema, o custo atual, o valor potencial.

## Formato de output

**Escreva:** `output/shape-01-opportunity.md`

```
## Usuário mais afetado
[Descrição por comportamento e contexto — não só cargo]

## Momento específico
Quando [X acontece], [Y fica impossível ou custoso].

## Custo atual
[Workaround descrito + esforço + o que é perdido]

## Valor de resolver
Para o usuário: [mudança concreta]
Para o negócio: [mudança concreta]

## Declaração de oportunidade
[1 parágrafo integrando os pontos acima]
```

## Critérios de aceite

- [ ] Usuário está descrito por comportamento e contexto, não só por cargo
- [ ] Momento específico usa o formato "quando X, Y"
- [ ] Custo atual é concreto — tem workaround descrito
- [ ] Declaração de oportunidade integra todos os elementos

## Gate

Automático — o agente continua para a task 02 imediatamente após concluir.
