# Padrões de Research — Kanvas

## Padrões identificados

### 1. O formato centrado no sistema sequestra a narrativa do time

Fontes: entrevistas 02 (Rafael), 03 (Carla), 06 (Thiago), 07 (Fernanda), 08 (Marcos), 09 (Sofia), 10 (Lucas) — **7 fontes independentes**

O relatório automático prioriza dados gerados pelo sistema (velocidade, tickets, percentual) como conteúdo principal. O espaço para contexto narrativo é limitado (campo com ~3 linhas) e posicionado como rodapé. O resultado: quem preenche sente que o relatório não representa o que realmente aconteceu — não pelo dado ser errado, mas porque o dado sem contexto distorce a realidade do trabalho.

Confirmação quantitativa: 21% dos tickets de suporte em Mai–Jun pedem "mais campos para informação". NPS de líderes de time = **-8** (incomum para esse segmento). Tempo médio de preenchimento cresceu de 8 min para 22 min — usuários tentam adicionar contexto onde o formato resiste.

Hipótese de causa raiz: Se o formato atual torna o sistema o narrador principal do que aconteceu na semana, então líderes de time percebem o relatório como uma representação que pode distorcer o desempenho do seu time — o que os desincentiva a preencher com cuidado ou a preencher em absoluto.

---

### 2. A ausência de loop de feedback visível quebra o incentivo de preenchimento

Fontes: entrevistas 06 (Thiago), 07 (Fernanda), 08 (Marcos), 09 (Sofia), 10 (Lucas) — **5 fontes independentes**

Líderes de time percebem que seus relatórios não geram reação visível dos gestores — nenhum comentário, nenhuma pergunta de follow-up, nenhuma ação decorrente do que foi relatado. Quando o relatório "vai para o vácuo", o produtor deixa de investir esforço. O ciclo se fecha: qualidade cai, gestor para de ler, produtor percebe que ninguém lê, qualidade cai mais.

Confirmação quantitativa: `report_configured` caiu **-37,9%** enquanto `report_viewed` caiu apenas **-10,6%**. Gestores continuam abrindo relatórios, mas líderes de time pararam de produzir — o que indica que o loop de feedback está quebrado no sentido gestor → líder, não o contrário. Marcos (08) testou empiricamente: levou um mês para o gestor notar que ele havia parado de preencher.

Hipótese de causa raiz: Se o produto não oferece um mecanismo visível de feedback do gestor para o produtor do relatório, então o líder de time não percebe que sua contribuição tem impacto — e racionalmente reduz o esforço até o mínimo necessário para não ter problema.

---

### 3. Usuários construíram substitutos externos que fazem o que o Kanvas não faz

Fontes: entrevistas 02 (Rafael), 03 (Carla), 04 (Bruno), 06 (Thiago), 10 (Lucas) — **5 fontes independentes**

Múltiplos usuários criaram alternativas paralelas espontâneas: planilha + email (Rafael), WhatsApp + transcrição manual (Bruno), Slack com template livre (Lucas), Notion com campos customizáveis (Thiago, Carla). Todos esses workarounds compartilham uma característica: dão ao produtor controle sobre o que e como comunicar. E todos têm maior adesão do que o Kanvas.

Confirmação quantitativa: `report_exported_csv` cresceu **+214,7%** de janeiro a junho — o maior crescimento de qualquer evento no período. Duas empresas entrevistadas já cancelaram e migraram para alternativas. Análise competitiva: Monday.com e Notion capturam usuários exatamente por oferecer flexibilidade de narrativa.

Hipótese de causa raiz: Se usuários estão construindo workarounds externos que têm maior adesão espontânea do que o produto, então o Kanvas não está perdendo para a concorrência direta — está perdendo para ferramentas genéricas que o próprio usuário adaptou. Isso significa que o problema não é posicionamento, é design de produto.

---

### 4. O design para o consumidor (gestor) ignora o produtor (líder de time)

Fontes: entrevistas 03 (Carla), 05 (Isabela), 09 (Sofia), 10 (Lucas) — **4 fontes independentes**, com evidência indireta em entrevistas 04 e 06

A feature foi otimizada para a experiência do gestor (quem lê). O único caso em que funciona bem (Isabela, 05) é quando a mesma pessoa ocupa os dois papéis. Quando há divisão — gestor consome, líder produz — o incentivo está invertido: o gestor se beneficia, o líder arCA com o esforço sem retorno claro.

Confirmação quantitativa: Queda de **-31%** nos líderes de time (configuradores) vs **-5,7%** nos gestores (visualizadores) de janeiro a junho. A feature está perdendo exatamente o grupo que a sustenta.

Hipótese de causa raiz: Se a feature foi desenhada priorizando a experiência de quem consome o relatório (gestor) em detrimento de quem o produz (líder de time), então quem produz não tem incentivo suficiente para sustentar o fluxo — e quando o produtor abandona, o consumidor também perde o valor.

---

## Sinais fracos (menos de 3 fontes)

- **Risco de exposição negativa por números sem contexto:** líder técnico relatado por Thiago (06) e Rafael (02) expressam que semanas difíceis — por razões legítimas — aparecem no relatório como baixa performance. Isso pode criar aversão ativa ao preenchimento, não apenas passividade. — 2 fontes diretas (potencialmente subnotificado)
- **Crescimento de tickets de suporte:** 82 tickets em Jan–Fev → 231 em Mai–Jun (+181%). "Como preencher" é 38% das categorias — sugere problema de onboarding/UX também. — fonte: analytics-report (1 fonte quantitativa)
- **Descrença na utilidade antes de tentar:** Carla (03) relata coordenadores que não preenchiam "por falta de tempo", mas revelaram depois que o real motivo era não se sentir representados. O motivo declarado pode mascarar o real. — 1 fonte direta

---

## Ranking de hipóteses

1. **O formato centrado no sistema sequestra a narrativa do time** — 7 fontes — confirmação quantitativa: sim (NPS -8, 21% dos tickets, crescimento do tempo de preenchimento)
2. **A ausência de loop de feedback visível quebra o incentivo de preenchimento** — 5 fontes — confirmação quantitativa: sim (queda -37,9% em configured vs -10,6% em viewed)
3. **Usuários construíram substitutos externos que fazem o que o Kanvas não faz** — 5 fontes — confirmação quantitativa: sim (+214,7% em export_csv)
4. **O design para o consumidor ignora o produtor** — 4 fontes — confirmação quantitativa: sim (queda -31% configuradores vs -5,7% visualizadores)
