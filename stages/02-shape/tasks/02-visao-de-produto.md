---
task_id: shape/visao-de-produto
processador: agente + aprovacao-humana
gate: humano
---

# Visão de Produto

## Objetivo

Definir o que estamos construindo e, tão importante quanto, o que não estamos.
Este é o maior gate de direção do processo — depois daqui, o sketch e o spec
fluem a partir desta visão.

Uma boa visão exclui tanto quanto inclui. Se a visão não exclui nada, ela não
está delimitando escopo — está apenas descrevendo uma intenção vaga.

## Contexto

Leia `output/shape-01-opportunity.md` e `output/01-research-summary.md`.

## Processador

Agente de IA, seguido de aprovação humana antes de continuar para o sketch.

## Passos

1. **Visão em 1 frase** — Use o template:
   "Para [quem], que [problema específico], o [nome] é [o quê] que [benefício
   central para o usuário]."
   Teste: se você trocar o nome do produto pelo de um concorrente e a frase
   ainda fizer sentido, a visão está genérica demais.

2. **É / Não é** — Crie uma tabela com 4-5 linhas. O "não é" deve listar coisas
   que as pessoas vão querer colocar no escopo mas que estão deliberadamente
   fora. Se o "não é" for óbvio demais, não vale a pena listar.

3. **Faz / Não faz** — Crie uma tabela com 4-5 linhas descrevendo
   funcionalidades concretas. O "não faz" é o escopo do MVP — o que é
   deliberadamente adiado para iterações posteriores.

4. **Usuário-alvo** — Descreva o usuário principal desta solução em 3 linhas,
   com base no que o Research revelou. Se há dois perfis relevantes, descreva
   os dois e indique o primário.

5. **Métricas de sucesso** — Liste 3 métricas concretas e mensuráveis que
   indicariam que a solução está funcionando. Métricas de negócio (churn,
   retenção) e métricas de produto (uso da feature, tempo na tarefa) podem
   coexistir.

## Formato de output

**Escreva:** `output/shape-02-vision.md`

```
## Visão
[1 frase]

## É / Não é
| É | Não é |
|---|-------|
|   |       |

## Faz / Não faz
| Faz | Não faz |
|-----|---------|
|     |         |

## Usuário-alvo
[3 linhas descritivas — primário e secundário se houver dois]

## Métricas de sucesso
1. [métrica — como medir]
2. [métrica — como medir]
3. [métrica — como medir]
```

## Critérios de aceite

- [ ] Visão está em 1 frase, não um parágrafo
- [ ] "Não é" exclui ao menos 3 coisas que seriam tentações de escopo
- [ ] "Não faz" é funcional e específico para o MVP
- [ ] Métricas são mensuráveis e têm método de medição indicado

## Gate

Humano — apresente a visão ao usuário e aguarde aprovação explícita.

Diga: "Aqui está a visão de produto. Isso captura o que queremos construir?
Posso continuar para o sketch?"

Não continue até receber confirmação.
