# PRD — Kanvas Weekly

## Problema

Líderes de time não conseguem comunicar o contexto real do seu trabalho semanal porque o Kanvas posiciona dados automáticos de projeto (velocidade, tickets, percentuais) como conteúdo principal do relatório e narrativa do time como detalhe secundário — fazendo o relatório representar mal o trabalho, desincentivando o preenchimento, e quebrando o ciclo de visibilidade que o produto prometia.

## Usuário-alvo

**Primário:** líder de time (tech lead, coordenador de área, engineering manager, customer success lead) em empresa de 50–300 funcionários que tem o contexto real do que aconteceu na semana e precisa transmitir esse contexto para um gestor que não acompanha o dia a dia. Tem NPS -8 com a feature atual. Hoje cria workarounds paralelos (email manual, Slack, WhatsApp, Notion) para fazer o que o Kanvas não permite.

**Secundário:** gestor (COO, VP, Head de Área) que precisa de visibilidade de múltiplos times sem reunião de status semanal. Tem NPS +34 mas perde valor quando o conteúdo que chega é raso ou inexistente.

## Visão do produto

Para líderes de time que precisam reportar progresso para gestores que não acompanham o trabalho diário, o Kanvas Weekly é uma atualização semanal estruturada que coloca a narrativa do time em primeiro lugar — com os dados automáticos do projeto como contexto, não como protagonistas.

## Faz / Não faz (MVP)

**Faz:**
- Abre o preenchimento semanal com campo de narrativa em destaque (o que aconteceu, o que ficou para trás, o que precisa de atenção)
- Salva rascunho automaticamente a cada 30 segundos
- Monta o relatório final com estrutura: narrativa do time → dados automáticos do projeto
- Envia notificação ao gestor quando o relatório fica disponível
- Exibe relatório ao gestor com narrativa em destaque, dados abaixo

**Não faz (MVP):**
- Processar texto com IA para sugestões automáticas
- Campos customizáveis por time ou empresa
- Loop de feedback estruturado do gestor para o líder
- Lembretes automáticos de preenchimento
- Integração com ferramentas externas (Slack, email direto)

## Métricas de sucesso

1. `report_configured` volta ao baseline de Janeiro (8.000+ eventos/mês) — analytics, avaliado 90 dias pós-lançamento
2. Taxa de relatórios enviados no prazo sobe de 52% para 70%+ — analytics, meta em 60 dias
3. Churn mid-market (50–300 func.) cai abaixo de 4% (de 6,8%) — CRM, avaliado no quarter seguinte

## User Stories — Onda 1 (MVP)

### US-01 — Preencher narrativa como destaque do relatório

Como líder de time que precisa reportar progresso semanal, quero escrever o que aconteceu, o que ficou para trás e o que precisa de atenção antes de ver os dados automáticos, para que o relatório que meu gestor recebe represente o trabalho real do time — não apenas números sem contexto.

**Critérios de aceite:**
- [ ] O campo "O que aconteceu esta semana" aparece acima dos dados automáticos na tela de preenchimento e tem destaque visual claro sobre eles
- [ ] O campo "O que ficou para trás" aparece como segundo campo de narrativa, marcado como obrigatório
- [ ] O campo "O que precisa de atenção da liderança" aparece como terceiro campo, marcado como opcional
- [ ] Cada campo de texto aceita no mínimo 1.000 caracteres
- [ ] Os dados automáticos aparecem abaixo dos campos de narrativa, em seção visualmente separada e secundária

**Tamanho:** M (3–5 dias)

---

### US-02 — Enviar relatório com narrativa + dados combinados

Como líder de time, quero enviar um relatório que combine minha narrativa com os dados automáticos do projeto, para que meu gestor receba contexto completo sem que eu precise criar comunicação paralela fora do Kanvas.

**Critérios de aceite:**
- [ ] O botão "Enviar relatório" fica ativo apenas quando os dois campos obrigatórios estão preenchidos
- [ ] Após o envio, o líder vê confirmação com nome e cargo do gestor que recebeu
- [ ] O relatório enviado combina narrativa + dados na mesma estrutura do preenchimento
- [ ] O líder não consegue enviar o mesmo relatório semanal duas vezes

**Tamanho:** M (3–5 dias) — depende de US-01

---

### US-03 — Salvar rascunho automaticamente sem perder conteúdo

Como líder de time que preenche o relatório em partes ao longo da semana, quero que meu rascunho seja salvo automaticamente, para que eu não perca o que escrevi se precisar sair da tela antes de enviar.

**Critérios de aceite:**
- [ ] O conteúdo é salvo automaticamente a cada 30 segundos enquanto há alteração não salva
- [ ] O status "Rascunho" aparece visível com timestamp da última gravação
- [ ] Ao retornar à tela da mesma semana, o rascunho é restaurado automaticamente
- [ ] O rascunho persiste até o envio ou até o fim da janela semanal configurada

**Tamanho:** P (1–2 dias) — depende de US-01

---

### US-04 — Gestor recebe relatório com narrativa em destaque

Como gestor que precisa de visibilidade dos times sem fazer reunião de status, quero receber um relatório onde a narrativa do time aparece em primeiro lugar, para que eu entenda o que aconteceu de verdade antes de interpretar os números.

**Critérios de aceite:**
- [ ] O email de notificação inclui a narrativa completa do time no corpo da mensagem
- [ ] No relatório dentro do Kanvas, a narrativa aparece acima dos dados automáticos
- [ ] O gestor acessa o relatório de qualquer time supervisionado em até 2 cliques
- [ ] O relatório indica claramente quem preencheu e quando foi enviado

**Tamanho:** M (3–5 dias) — depende de US-02

---

## User Stories — Onda 2+ (adiado)

- **US-05** — Consultar histórico de relatórios anteriores como referência (P) — útil mas não bloqueia validação do MVP
- Loop de feedback do gestor para o líder — resolve Padrão 2 do Research, mas causa secundária; entra após confirmar que preenchimento voltou
- Lembretes automáticos de preenchimento — o Research mostrou que o problema não é esquecimento, é formato; entra depois de validar o formato
- Campos customizáveis por time — deliberadamente adiado; estrutura fixa da Onda 1 é uma decisão de produto, não limitação técnica
