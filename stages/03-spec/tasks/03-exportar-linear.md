---
task_id: spec/exportar-linear
processador: agente + ferramenta-externa (Linear via MCP)
gate: automatico
---

# Exportar para o Linear

## Objetivo

Criar o projeto e as tasks no Linear com base no plano de build aprovado.
Este é o output final do workflow — depois daqui, o trabalho está pronto
para começar.

## Contexto

Leia `output/spec-01-user-stories.md` e `output/spec-02-build-plan.md`.
Use apenas as stories da Onda 1 para o Linear.

## Processador

Agente de IA + Ferramenta externa: Linear (via MCP `mcp__linear__save_project`
e `mcp__linear__save_issue`)

Fallback automático se Linear indisponível: escrever `output/linear-tasks.json`
com o mesmo conteúdo estruturado.

## Passos

1. **Verificar Linear** — Chame `mcp__linear__list_teams` para verificar
   disponibilidade e obter o team ID disponível.

2. **Gerar PRD** — Antes de qualquer exportação, escreva `output/spec-prd.md`
   consolidando o documento de produto completo:

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

   ### User Stories (Onda 1)
   [Lista completa de stories com critérios de aceite]

   ### User Stories (Onda 2+)
   [Lista resumida — adiado]
   ```

3. **Se Linear disponível:**
   - Crie o projeto com `mcp__linear__save_project`:
     - `name`: nome do produto
     - `description`: visão do produto (1-2 frases do PRD)
     - `teamIds`: [team ID obtido no passo 1]
   - Registre o ID do projeto criado.
   - Crie o PRD como documento do projeto com `mcp__linear__save_document`:
     - `title`: "PRD — [nome do produto]"
     - `content`: conteúdo completo do `output/spec-prd.md` em markdown
     - `project`: ID do projeto criado acima
   - Para cada story da Onda 1, crie uma issue com `mcp__linear__save_issue`:
     - `title`: título curto e acionável da story
     - `description`: texto completo da story + critérios de aceite formatados
       em markdown
     - `project`: ID do projeto criado acima
     - Inclua o tamanho estimado (P/M/G) na descrição
     - Se houver URL do sketch (Lovable ou outro), inclua em `links`:
       `[{"url": "[url-do-sketch]", "title": "Sketch — [nome do produto]"}]`
   - Registre o ID e link de cada issue criada.

4. **Se Linear indisponível (fallback):**
   - Escreva `output/linear-tasks.json` com os mesmos dados:
     ```json
     [
       {
         "title": "",
         "description": "",
         "estimate": "",
         "story_id": ""
       }
     ]
     ```
   - Informe ao usuário que o fallback foi usado e onde está o arquivo.

5. **Summary final** — Escreva `output/03-spec-summary.md` consolidando todo
   o processo: do problema ao plano, com links das issues criadas.

## Formato de output

**Escreva:** `output/spec-prd.md` (passo 2) e `output/03-spec-summary.md` (passo 5)

```
## Spec Summary — [nome do produto]

### O problema resolvido
[Declaração do problema do Research em 1 frase]

### A aposta
[Visão em 1 frase do Shape]

### Tasks criadas (Onda 1)

| Story | Título | Tamanho | Link |
|-------|--------|---------|------|

### Onda 2+ (adiado)
[Lista resumida]

### Próximos passos
[O que acontece depois do MVP ser construído]
```

Se fallback: `output/linear-tasks.json`

## Critérios de aceite

- [ ] `output/spec-prd.md` foi escrito com problema, visão, faz/não faz, métricas e stories
- [ ] Projeto criado no Linear com `save_project` antes de criar issues
- [ ] PRD criado como documento do projeto com `save_document`
- [ ] Todas as stories da Onda 1 foram exportadas (Linear ou JSON)
- [ ] Cada issue tem título, descrição com story completa, critérios de aceite e `project`
- [ ] Link do sketch adicionado em cada issue via `links`
- [ ] `output/03-spec-summary.md` foi escrito e conecta o problema à solução
- [ ] Links do Linear estão registrados (ou caminho do JSON de fallback)

## Gate

Automático — este é o último passo do workflow.

Após concluir, diga: "O workflow está completo. Aqui está o summary final."
E apresente `output/03-spec-summary.md`.
