# Cola do Exercício — Análise de Entrevistas

Use este arquivo durante a demonstração ao vivo.
Este arquivo cobre as duas partes: decomposição e preenchimento do template.

---

## PARTE 1 — Decomposição

### Pergunta 1: Quais são as etapas em ordem?

```
1. Ler cada entrevista e extrair sinais (o que a pessoa fez, o que disse querer)
2. Classificar cada sinal: comportamental ou atitudinal
3. Pegar os dados quantitativos (analytics) e extrair tendências
4. Cruzar qualitativo com quantitativo — onde confirmam, onde contradizem
5. Identificar lacunas — o que falta para ter uma visão completa
6. Validar o mapa com quem conhece o produto
```

### Pergunta 2: O que precisa estar pronto antes de cada etapa?

```
- Transcrições das entrevistas (para as etapas 1, 2, 4, 5)
- Relatório de analytics (para as etapas 3, 4)
- As etapas são sequenciais — cada uma depende da anterior
```

### Pergunta 3: Quem tem capacidade de executar?

```
- Ler e extrair sinais → LLM (leitura + classificação com critério claro)
- Classificar comportamental/atitudinal → LLM
- Extrair tendências de analytics → LLM
- Cruzar e identificar contradições → LLM
- Validar se o diagnóstico faz sentido → Humano (precisa de contexto do negócio)
```

### Pergunta 4: Qual etapa precisa de validação antes de continuar?

```
A última — o mapa de evidências completo.
As etapas de leitura e classificação são recuperáveis se errarem.
O mapa consolidado é o input para tudo que vem depois:
se estiver errado, toda a análise seguinte fica comprometida.
→ Gate humano antes de continuar.
```

### Tabela resultante

| Etapa | Input | Quem executa | Gate |
|-------|-------|--------------|------|
| Extrair sinais de cada entrevista | Transcrições | LLM | Automático |
| Classificar comportamental/atitudinal | Sinais extraídos | LLM | Automático |
| Extrair tendências dos dados | Analytics | LLM | Automático |
| Cruzar e identificar contradições | Sinais + analytics | LLM | Automático |
| Identificar lacunas | Tudo acima | LLM | Automático |
| Validar o mapa | Mapa de evidências | Humano (PM) | Gate humano |

---

## PARTE 2 — Preenchimento do template

---

## CAMPO: task_id
```
research/mapear-evidencias
```

## CAMPO: processador
```
agente
```

## CAMPO: gate
```
humano
```

---

## CAMPO: Objetivo
```
Fazer um inventário completo das evidências coletadas nas entrevistas e
classificar cada sinal como comportamental (o que os usuários fazem) ou
atitudinal (o que dizem que querem). Esta task não tira conclusões —
ela organiza o material para que a análise posterior seja confiável.
```

---

## CAMPO: Contexto
```
Fontes disponíveis:
- Transcrições das entrevistas realizadas
- Relatório de analytics do produto (se houver)
- Análise de concorrentes (se houver)
```

---

## CAMPO: Processador
```
Agente de IA
```

---

## CAMPO: Passos
```
1. **Entrevistas** — Leia cada entrevista individualmente. Para cada uma, extraia:
   - Perfil da pessoa: cargo, empresa, contexto
   - O que FAZIA antes de reclamar (sinal comportamental — ação concreta)
   - O que DIZ que quer (sinal atitudinal — opinião, pedido, preferência)
   - Cite trechos diretos quando possível

2. **Dados quantitativos** — Se houver analytics, extraia:
   - Tendências principais (o que sobe, o que cai)
   - Números com período de referência
   Registre como sinais quantitativos — não interprete ainda.

3. **Cruzamento** — Identifique onde sinais qualitativos e quantitativos
   se confirmam, e onde contradizem.

4. **Lacunas** — Registre o que está faltando para ter uma visão completa.
   Estime o impacto de cada lacuna na qualidade da análise.
```

---

## CAMPO: Formato de output
```
**Escreva:** `output/mapa-de-evidencias.md`

## Sinais comportamentais
(o que os usuários fazem — ações observadas ou descritas)
- [sinal] — fonte: [entrevista]

## Sinais atitudinais
(o que os usuários dizem que querem)
- [sinal] — fonte: [entrevista]

## Contradições
- [comportamento] vs [discurso] — fonte: [entrevista]

## Lacunas
- [lacuna] — impacto: [alto | médio | baixo]
```

---

## CAMPO: Critérios de aceite
```
- [ ] Todas as entrevistas foram processadas individualmente
- [ ] Sinais comportamentais e atitudinais estão separados
- [ ] Cada sinal cita a fonte de origem
- [ ] Contradições entre comportamento e discurso foram sinalizadas
- [ ] Lacunas estão registradas com impacto estimado
```

---

## CAMPO: Gate
```
Humano — apresente o mapa de evidências e aguarde aprovação antes de continuar.

Diga: "Aqui está o mapa de evidências. Isso captura o que você ouviu nas
entrevistas? Posso continuar para a extração de padrões?"
```

---

## AO FINAL — mostrar o contrato real

Abrir: `stages/01-research/tasks/01-mapear-evidencias.md`

Mostrar que o que acabamos de construir é equivalente ao contrato que
roda no workflow. Engenharia reversa completa.
