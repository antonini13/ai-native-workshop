---
task_id: spec/user-stories
processador: agente
gate: automatico
---

# User Stories

## Objetivo

Traduzir a visão de produto em histórias de usuário acionáveis, com critérios
de aceite claros. As stories são a unidade de trabalho do time de desenvolvimento
— precisam ser específicas o suficiente para serem implementadas sem precisar
de uma reunião para explicar o que foi pedido.

Uma story mal escrita é ambígua: o desenvolvedor implementa uma coisa, o PM
esperava outra. Um critério de aceite bem escrito elimina essa ambiguidade.

## Contexto

Leia `output/02-shape-summary.md` e `output/shape-02-vision.md`.

## Processador

Agente de IA

## Passos

1. **Jornadas principais** — Identifique as 3-5 jornadas centrais que a solução
   precisa suportar para resolver o problema identificado no Research. Uma
   jornada é uma sequência de ações que o usuário realiza para atingir um
   objetivo.

2. **Escrever stories** — Para cada jornada, escreva 1-2 stories no formato:
   "Como [usuário específico], quero [ação concreta], para que [resultado
   tangível]."
   O "para que" deve ser um resultado real para o usuário, não para o sistema
   ou para o negócio.

3. **Critérios de aceite** — Para cada story, liste 2-4 critérios específicos
   e verificáveis. Um critério verificável tem resposta binária: passou ou
   não passou. "O usuário consegue adicionar contexto ao relatório" não é
   verificável — "o campo de contexto aceita até 500 caracteres e é salvo
   automaticamente a cada 30 segundos" é verificável.

4. **Marcação de MVP** — Identifique quais stories são essenciais para a
   Onda 1 (MVP) versus quais podem ser iterações posteriores. MVP é o mínimo
   que valida a aposta de produto — não o mínimo possível de esforço.

## Formato de output

**Escreva:** `output/spec-01-user-stories.md`

```
## Stories

### US-01 — [Título curto e descritivo]
Como [usuário específico], quero [ação concreta], para que [resultado tangível].

**Critérios de aceite:**
- [ ] [critério específico e verificável]
- [ ] [critério específico e verificável]

**Onda:** MVP

---

[repetir para cada story]
```

## Critérios de aceite

- [ ] 5-8 stories escritas
- [ ] Cada story tem 2 ou mais critérios de aceite específicos e verificáveis
- [ ] Stories MVP estão marcadas
- [ ] O "para que" de cada story é um resultado para o usuário, não para o sistema
- [ ] Stories partem da perspectiva do usuário — não começam com "o sistema deve"

## Gate

Automático — o agente continua para a task 02 imediatamente após concluir.
