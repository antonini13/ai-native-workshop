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

Leia `output/spec-02-build-plan.md`. Use apenas as stories da Onda 1.

## Processador

Agente de IA + Ferramenta externa: Linear (via MCP `mcp__linear__save_issue`)

Fallback automático se Linear indisponível: escrever `output/linear-tasks.json`
com o mesmo conteúdo estruturado.

## Passos

1. **Verificar Linear** — Chame `mcp__linear__list_teams` para verificar
   disponibilidade e obter o team ID disponível.

2. **Se Linear disponível:**
   - Para cada story da Onda 1, crie uma issue com `mcp__linear__save_issue`:
     - `title`: título curto e acionável da story
     - `description`: texto completo da story + critérios de aceite formatados
       em markdown
     - Inclua o tamanho estimado (P/M/G) na descrição
   - Registre o ID e link de cada issue criada.

3. **Se Linear indisponível (fallback):**
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

4. **Summary final** — Escreva `output/03-spec-summary.md` consolidando todo
   o processo: do problema ao plano, com links das issues criadas.

## Formato de output

**Escreva:** `output/03-spec-summary.md`

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

- [ ] Todas as stories da Onda 1 foram exportadas (Linear ou JSON)
- [ ] Cada issue tem título, descrição com story completa e critérios de aceite
- [ ] `output/03-spec-summary.md` foi escrito e conecta o problema à solução
- [ ] Links do Linear estão registrados (ou caminho do JSON de fallback)

## Gate

Automático — este é o último passo do workflow.

Após concluir, diga: "O workflow está completo. Aqui está o summary final."
E apresente `output/03-spec-summary.md`.
