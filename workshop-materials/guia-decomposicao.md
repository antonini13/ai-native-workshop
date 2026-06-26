# Guia de Decomposição — Da tarefa ao contrato de sistema

## A tese

Falar com usuários gera grande valor. Mas o trabalho que vem depois —
transcrever, organizar, separar sinal de ruído, cruzar com dados — exige
tempo e experiência que a maioria dos times não tem de sobra. Os mais
experientes estão ocupados. Os menos experientes não sabem por onde começar.

O resultado: o valor da entrevista fica preso na cabeça de quem fez.
Não vira decisão. Não vira sistema.

A proposta: decompor esse trabalho em passos claros e transformá-lo em um
contrato que um agente consegue executar — liberando o humano para o que
só ele consegue fazer: a conversa em si e o julgamento final.

---

## Parte 1 — Decomposição (pensamento humano)

Antes de qualquer sistema, o trabalho é entender a tarefa.
Quatro perguntas para decompor:

**1. Quais são as etapas dessa tarefa em ordem?**
Liste o que acontece do início ao fim. Seja específico — "analisar" não é
uma etapa, é um rótulo. O que exatamente você faz quando analisa?

**2. O que precisa estar pronto antes de começar cada etapa?**
Inputs, contexto, decisões anteriores. Uma etapa sem input claro é uma
etapa que vai falhar ou gerar resultado inconsistente.

**3. Em cada etapa, quem tem capacidade de executar?**
- É leitura, classificação, síntese estruturada com critério claro? → LLM
- Precisa de uma ferramenta externa (busca, planilha, API)? → LLM + ferramenta
- Precisa de julgamento, experiência ou aprovação de quem tem contexto? → Humano

**4. O resultado de cada etapa precisa de validação antes de continuar?**
Se a etapa seguinte depende de que o resultado esteja correto, um humano
precisa aprovar. Se o erro é recuperável ou a etapa seguinte vai detectar,
pode ser automático.

---

## Parte 2 — Formalização (contrato de sistema)

Com a decomposição feita, o contrato é o documento que traduz o raciocínio
humano para uma forma que o agente consegue seguir de forma consistente.

Cada campo do contrato responde uma pergunta específica:

| Campo | Pergunta que responde |
|-------|-----------------------|
| `## Objetivo` | Por que essa task existe? O que ela entrega e o que deliberadamente não faz? |
| `## Contexto` | O que precisa estar disponível antes de começar? |
| `## Processador` | Quem executa — agente, humano ou combinação? |
| `## Passos` | Qual é a sequência exata de ações? |
| `## Formato de output` | Como é o resultado — estrutura, seções, campos? |
| `## Critérios de aceite` | Como verifico que o output está correto? |
| `## Gate` | A próxima etapa começa automaticamente ou precisa de aprovação? |

---

## Exemplo aplicado: análise de entrevistas pós-discovery

**A tarefa (como a maioria faz hoje):**
Após 10 entrevistas com usuários, alguém — geralmente o PM mais sênior —
lê as transcrições, tenta lembrar o que ouviu, anota pontos soltos numa
planilha ou Notion, e produz um "resumo" que depende completamente de quem
fez e de quanto tempo tinha.

**Decomposição:**

| Etapa | Input | Quem executa | Gate |
|-------|-------|--------------|------|
| Ler cada entrevista e extrair sinais | Transcrições | LLM | Automático |
| Separar comportamental de atitudinal | Sinais extraídos | LLM | Automático |
| Cruzar com dados quantitativos | Sinais + analytics | LLM | Automático |
| Identificar contradições e lacunas | Tudo acima | LLM | Automático |
| Validar o diagnóstico | Mapa de evidências | Humano (PM) | Gate humano |

**Por que o humano entra só no final?**
As etapas anteriores são leitura e classificação com critério explícito —
LLM faz bem. O julgamento sobre se o diagnóstico faz sentido para o contexto
do produto é o que só quem conhece o negócio consegue fazer.

**O contrato pronto:** `stages/01-research/tasks/01-mapear-evidencias.md`

Abra esse arquivo. Cada campo do contrato é o resultado direto da
decomposição acima.
