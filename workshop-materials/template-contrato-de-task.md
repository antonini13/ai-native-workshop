---
task_id: [stage]/[nome-da-task]
processador: [agente | humano | agente + ferramenta-externa | agente + aprovacao-humana]
gate: [automatico | humano]
---

# [Nome da Task]

## Objetivo

[O que essa task faz e por que ela existe no processo.
Uma boa descrição diz o que a task NÃO faz também — deixa claro o escopo.]

## Contexto

[O que o agente precisa ler ou saber antes de começar.
Liste arquivos de input, dados disponíveis, outputs de tasks anteriores.]

## Processador

[Quem ou o quê executa essa task:
- Agente de IA
- Humano
- Agente de IA + Ferramenta externa: [nome da ferramenta]
- Agente de IA + aprovação humana antes de continuar]

## Passos

[Sequência numerada de ações. Cada passo deve ser específico o suficiente
para que o agente saiba exatamente o que fazer — sem ambiguidade.]

1. **[Nome do passo]** — [descrição]
2. **[Nome do passo]** — [descrição]
3. ...

## Formato de output

**Escreva:** `output/[nome-do-arquivo].md`

[Defina a estrutura exata do arquivo gerado — seções, tabelas, campos.
O agente vai seguir esse formato literalmente.]

## Critérios de aceite

[Checklist binário: passou ou não passou. Cada critério deve ser verificável
sem interpretação — ou está lá ou não está.]

- [ ] [critério específico e verificável]
- [ ] [critério específico e verificável]
- [ ] [critério específico e verificável]

## Gate

[Automático — o agente continua para a task seguinte imediatamente após concluir.]

ou

[Humano — apresente o resultado ao usuário e aguarde aprovação explícita antes
de continuar. Diga: "[frase exata que o agente vai usar para pedir aprovação]"]
