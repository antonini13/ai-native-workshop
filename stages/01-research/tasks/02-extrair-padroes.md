---
task_id: research/extrair-padroes
processador: agente
gate: automatico
---

# Extrair Padrões

## Objetivo

Identificar padrões que emergem de múltiplas fontes independentes. Um sinal
isolado é ruído — pode ser o caso especial de um usuário específico. Um padrão
que aparece em 3 ou mais fontes distintas começa a ser evidência.

Esta task transforma o inventário de sinais em hipóteses ranqueadas sobre a
causa raiz do problema.

## Contexto

Leia `output/research-01-evidence-map.md` como input principal.

## Processador

Agente de IA

## Passos

1. **Agrupamento** — Agrupe sinais similares do mapa de evidências. Dê um nome
   curto e descritivo para cada cluster. Um bom nome descreve o padrão, não
   apenas o sintoma: "esforço de preenchimento não compensa o retorno" é melhor
   que "formulário ruim".

2. **Filtro de padrão** — Mantenha apenas clusters com 3 ou mais fontes distintas.
   Mova o restante para uma lista de "sinais fracos" — registre, mas não analise
   profundamente. Sinais fracos podem ser relevantes mais tarde.

3. **Cruzamento quantitativo** — Para cada padrão forte, verifique se há dado
   de métrica que confirma ou contradiz. Registre o cruzamento explicitamente,
   inclusive quando não há dado disponível.

4. **Hipóteses de causa raiz** — Para cada padrão forte, formule uma hipótese:
   "Se este é o padrão, então a causa raiz pode ser X, porque Y."
   Uma hipótese é testável. "O produto é ruim" não é hipótese — é julgamento.

5. **Ranking** — Ordene as hipóteses por força de evidência: quantas fontes
   independentes sustentam, quão direta é a relação com o problema declarado
   no onboarding, se há confirmação quantitativa.

## Formato de output

**Escreva:** `output/research-02-patterns.md`

```
## Padrões identificados

### [Nome do padrão]
Fontes: [lista de referências — mínimo 3]
Confirmação quantitativa: [dado de métrica] ou [não confirmado — lacuna]
Hipótese de causa raiz: [declaração testável]

[repetir para cada padrão forte]

## Sinais fracos (menos de 3 fontes)
- [sinal] — [1-2 fontes]

## Ranking de hipóteses
1. [hipótese mais forte] — [N fontes] — confirmação quantitativa: [sim | não]
2. ...
```

## Critérios de aceite

- [ ] Cada padrão cita ao menos 3 fontes distintas
- [ ] Hipóteses são declarações testáveis, não julgamentos
- [ ] Cruzamento com dados quantitativos está presente para cada padrão
- [ ] Ranking de hipóteses está explícito e justificado
- [ ] Sinais fracos estão registrados separadamente

## Gate

Automático — o agente continua para a task 03 imediatamente após concluir.
