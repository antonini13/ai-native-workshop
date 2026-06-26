---
task_id: research/mapear-evidencias
processador: agente
gate: automatico
---

# Mapear Evidências

## Objetivo

Fazer um inventário completo das evidências disponíveis e classificar cada sinal
como comportamental (o que os usuários fazem) ou atitudinal (o que dizem que
querem). Esta task não tira conclusões — ela organiza o material para que a
análise posterior seja confiável.

Um sinal comportamental é uma ação: o usuário exportou para Excel, parou de
preencher o formulário, criou um ritual alternativo no Slack. Um sinal atitudinal
é uma declaração: "o sistema é chato", "eu queria que tivesse um campo de
contexto", "não vale o esforço". A distinção importa porque o que as pessoas
fazem frequentemente contradiz o que dizem que querem.

## Contexto

Leia `output/00-onboarding-summary.md` antes de começar.

Fontes disponíveis:
- `data/interviews/` — 10 entrevistas com usuários
- `data/metrics/analytics-report.md` — dados de analytics do produto
- `data/competitive/competitor-analysis.md` — análise de concorrentes

## Processador

Agente de IA

## Passos

Processe um tipo de fonte por vez. Não misture fontes antes de terminar
cada grupo.

1. **Entrevistas** — Leia cada entrevista individualmente. Para cada uma, extraia:
   - Quem é a pessoa: perfil, tipo de empresa, tamanho da equipe
   - Qual problema descreve
   - O que FAZIA antes de reclamar (sinal comportamental — ação concreta)
   - O que DIZ que quer (sinal atitudinal — opinião, pedido, preferência declarada)
   - Cite trechos diretos quando possível

2. **Métricas** — Leia o relatório de analytics. Extraia:
   - Tendências principais (o que está subindo, o que está caindo)
   - Números específicos com período de referência
   - Correlações entre métricas
   Registre como sinais quantitativos — não interprete ainda.

3. **Concorrentes** — Leia a análise de concorrentes. Registre:
   - Como cada concorrente aborda o mesmo problema
   - Sinais de mercado relevantes para o problema investigado

4. **Cruzamento** — Identifique onde os sinais qualitativos e quantitativos
   se confirmam mutuamente, e onde contradizem.

5. **Lacunas** — Registre o que está faltando para ter uma visão mais completa.
   Estime o impacto de cada lacuna na qualidade da análise.

## Formato de output

**Escreva:** `output/research-01-evidence-map.md`

```
## Fontes disponíveis
| Fonte | Tipo | Perfil / Período | Confiança |
|-------|------|-----------------|-----------|

## Sinais comportamentais
(o que os usuários fazem — ações observadas ou descritas)
- [sinal] — fonte: [referência]

## Sinais atitudinais
(o que os usuários dizem que querem — opiniões, pedidos, reclamações)
- [sinal] — fonte: [referência]

## Contradições
(onde o que fazem contradiz o que dizem)
- [comportamento observado] vs [discurso declarado] — fonte: [referência]

## Lacunas
(o que está faltando para uma visão mais completa)
- [lacuna] — impacto: [alto | médio | baixo]
```

## Critérios de aceite

- [ ] Todas as 10 entrevistas foram processadas individualmente
- [ ] Sinais comportamentais e atitudinais estão separados e claramente distintos
- [ ] Cada sinal cita a fonte de origem
- [ ] Contradições entre comportamento e discurso foram sinalizadas
- [ ] Lacunas estão registradas com impacto estimado

## Gate

Automático — o agente continua para a task 02 imediatamente após concluir.
