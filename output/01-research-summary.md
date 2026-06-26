# Research Summary — Stage 1

## Declaração do problema

O problema é que líderes de time não conseguem comunicar o contexto real do seu trabalho semanal porque o Kanvas posiciona dados automáticos de projeto (velocidade, tickets, percentuais) como conteúdo principal do relatório e narrativa do time como detalhe secundário — fazendo o relatório representar mal o trabalho, desincentivando o preenchimento, e quebrando o ciclo de visibilidade que o produto prometia.

---

## Top 3 evidências

1. **`report_exported_csv` cresceu +214,7% (de 340 para 1.070 eventos em 6 meses) + múltiplos relatos de usuários exportando dados e construindo comunicação manual fora do sistema** — fontes: Analytics + Entrevistas 02 (Rafael), 04 (Bruno), 10 (Lucas) — sustenta porque: prova que o problema não é falta de motivação ou tempo, mas sim que o formato do produto não permite o que os usuários precisam comunicar. Eles fazem o trabalho — só que fora do produto.

2. **NPS líderes de time: -8 vs gestores: +34 (diferença de 42 pontos), com queda assimétrica no uso: -31% líderes vs -5,7% gestores** — fonte: Analytics — sustenta porque: a insatisfação está cirurgicamente localizada no produtor do conteúdo. Os gestores ainda tentam consumir (-5,7%) mas os líderes estão abandonando (-31%). É um colapso pelo lado da oferta, não da demanda.

3. **Cinco entrevistados independentes (Rafael, Bruno, Carla, Thiago, Lucas) criaram sistemas paralelos distintos (email manual, WhatsApp + síntese, Notion, Slack com template) que convergem para a mesma estrutura: narrativa livre do time + dados como apoio** — fontes: Entrevistas 02, 03, 04, 06, 10 — sustenta porque: convergência independente revela qual é o produto que os usuários estão tentando construir por conta própria. É o briefing implícito do que o Kanvas precisaria ser.

---

## Insight principal

O onboarding levantou três hipóteses do time: problema de UX, falha na ativação, mudança de mercado. O Research revelou que todas as três estão erradas como causa raiz.

**O que ficou claro que não era óbvio antes:** os líderes de time não são relutantes ou preguiçosos. Eles são motivados o suficiente para construir sistemas paralelos trabalhosos — WhatsApp, Slack, planilhas, emails semanais — para fazer o que o Kanvas não permite. A disposição de comunicar existe. O que falta é o formato certo dentro do produto.

O problema central é de design: o Kanvas foi arquitetado tendo o gestor como usuário primário, mas quem decide se o produto tem conteúdo é o líder de time. A feature de Relatórios Automáticos funciona bem quando a mesma pessoa é simultaneamente quem sabe o contexto e quem preenche (Isabela Costa é o único caso de satisfação — e é exatamente esse o seu perfil). Quando há separação estrutural entre produtor e consumidor, a arquitetura atual garante o colapso: o produtor não se sente representado, para de se esforçar, e o gestor perde o que lia.

A simplificação do formulário e a campanha de reengajamento falharam porque não tocaram nessa assimetria. Foram respostas a sintomas.

---

## O que ainda não sabemos

- Como os gestores se comportam após receber os relatórios — quantos respondem, perguntam, reagem — impacto na confiança: **médio** (confirmaria ou refutaria o feedback loop como causa secundária; não muda a direção principal)
- Qual percentual de líderes de time criou workarounds vs simplesmente parou de usar — impacto na confiança: **médio** (ajudaria a estimar tamanho do segmento que tem disposição de mudar de comportamento com o produto certo)
- Se há problema de ativação — novos usuários que tentaram e desistiram antes de completar o primeiro relatório — impacto na confiança: **baixo** (a queda é em usuários que já usavam; ativação não explica a saída)

---

## Pergunta de design para o Shape

Como poderíamos permitir que o líder de time conte a história do que aconteceu antes dos dados automáticos chegarem ao gestor, sem aumentar a carga de trabalho de preenchimento?
