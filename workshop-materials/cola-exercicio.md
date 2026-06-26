# Cola do Exercício — Análise de Entrevistas

Use este arquivo durante a demonstração ao vivo.
Cole cada campo no template conforme for preenchendo.

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
