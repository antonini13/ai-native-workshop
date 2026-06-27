---
task_id: spec/exportar-tasks
processador: agente
gate: automatico
---

# Exportar Tasks

## Objetivo

Gerar o PRD completo e as tasks da Onda 1 em formato estruturado, pronto para
importar na ferramenta de gestão do time (Linear, Jira, Notion, Trello, etc.).

## Contexto

Leia `output/spec-01-user-stories.md` e `output/spec-02-build-plan.md`.
Use apenas as stories da Onda 1.

## Processador

Agente de IA

## Passos

1. **Gerar PRD** — Escreva `output/spec-prd.md` consolidando o documento de
   produto completo:

   ```
   ## PRD — [nome do produto]

   ### Problema
   [Declaração do problema validada no Research]

   ### Usuário-alvo
   [Persona principal com contexto]

   ### Visão do produto
   [Aposta em 1-2 frases do Shape]

   ### Faz / Não faz (MVP)
   **Faz:** ...
   **Não faz:** ...

   ### Métricas de sucesso
   [KPIs definidos no Shape]

   ### User Stories — Onda 1
   [Lista completa de stories com critérios de aceite]

   ### User Stories — Onda 2+
   [Lista resumida — adiado]
   ```

2. **Gerar tasks em JSON** — Escreva `output/tasks.json` com as stories da
   Onda 1 em formato estruturado:

   ```json
   [
     {
       "story_id": "US-01",
       "title": "",
       "description": "",
       "estimate": "P | M | G",
       "depends_on": []
     }
   ]
   ```

   Inclua na `description` o texto completo da story + critérios de aceite
   formatados em markdown. Respeite a ordem de dependências no array.

3. **Summary final** — Escreva `output/03-spec-summary.md` consolidando todo
   o processo: do problema ao plano.

## Formato de output

**Escreva:** `output/spec-prd.md`, `output/tasks.json` e `output/03-spec-summary.md`

```
## Spec Summary — [nome do produto]

### O problema resolvido
[Declaração do problema do Research em 1 frase]

### A aposta
[Visão em 1 frase do Shape]

### Tasks — Onda 1

| Story | Título | Tamanho | Depende de |
|-------|--------|---------|------------|

**Estimativa total:** [N–N dias úteis]

*Tasks exportadas em `output/tasks.json` — importe na ferramenta de gestão do seu time.*

### Onda 2+ (adiado)
[Lista resumida com justificativa de adiamento]

### Próximos passos
[O que acontece depois do MVP ser construído]
```

## Critérios de aceite

- [ ] `output/spec-prd.md` foi escrito com problema, visão, faz/não faz, métricas e stories
- [ ] `output/tasks.json` contém todas as stories da Onda 1 com título, descrição e estimativa
- [ ] Dependências entre tasks estão registradas no campo `depends_on`
- [ ] `output/03-spec-summary.md` conecta o problema à solução e referencia o JSON

## Gate

Automático — continua imediatamente para a geração do report visual.

Após concluir, diga: "Tasks exportadas em `output/tasks.json`. Importe na
ferramenta de gestão do seu time. Gerando o report final agora."
