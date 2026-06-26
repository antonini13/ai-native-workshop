# User Stories — Spec Stage 1

## Stories

### US-01 — Preencher narrativa como destaque do relatório

Como líder de time que precisa reportar progresso semanal, quero escrever o que aconteceu, o que ficou para trás e o que precisa de atenção antes de ver os dados automáticos, para que o relatório que meu gestor recebe represente o trabalho real do time — não apenas números sem contexto.

**Critérios de aceite:**
- [ ] O campo "O que aconteceu esta semana" aparece acima dos dados automáticos na tela de preenchimento e tem destaque visual claro (tamanho, hierarquia) sobre eles
- [ ] O campo "O que ficou para trás" aparece como segundo campo de narrativa, marcado como obrigatório
- [ ] O campo "O que precisa de atenção da liderança" aparece como terceiro campo, marcado como opcional
- [ ] Cada campo de texto aceita no mínimo 1.000 caracteres sem truncar ou desabilitar a edição
- [ ] Os dados automáticos do projeto (velocidade, tickets, status) aparecem abaixo dos campos de narrativa, em seção visualmente separada e secundária

**Onda:** MVP

---

### US-02 — Enviar relatório com narrativa + dados combinados

Como líder de time, quero enviar um relatório que combine minha narrativa com os dados automáticos do projeto, para que meu gestor receba contexto completo sem que eu precise criar comunicação paralela fora do Kanvas.

**Critérios de aceite:**
- [ ] O botão "Enviar relatório" fica ativo apenas quando os dois campos obrigatórios (o que aconteceu e o que ficou para trás) estão preenchidos
- [ ] Após o envio, o líder vê confirmação com nome e cargo do gestor que recebeu o relatório
- [ ] O relatório enviado combina narrativa + dados na mesma estrutura que o líder visualizou durante o preenchimento
- [ ] O líder não consegue enviar o mesmo relatório semanal duas vezes — o sistema indica que o relatório da semana já foi enviado

**Onda:** MVP

---

### US-03 — Salvar rascunho automaticamente sem perder conteúdo

Como líder de time que preenche o relatório em partes ao longo da semana, quero que meu rascunho seja salvo automaticamente, para que eu não perca o que escrevi se precisar sair da tela antes de enviar.

**Critérios de aceite:**
- [ ] O conteúdo é salvo automaticamente a cada 30 segundos enquanto há alteração não salva
- [ ] O status "Rascunho" aparece visível na interface com timestamp da última gravação ("Salvo há 2 minutos")
- [ ] Ao retornar à tela de preenchimento da mesma semana, o conteúdo do rascunho é restaurado automaticamente sem ação do usuário
- [ ] O rascunho persiste até o envio do relatório ou até o fim da janela semanal configurada pelo time

**Onda:** MVP

---

### US-04 — Gestor recebe relatório com narrativa em destaque

Como gestor que precisa de visibilidade dos times sem fazer reunião de status, quero receber um relatório onde a narrativa do time aparece em primeiro lugar, para que eu entenda o que aconteceu de verdade antes de interpretar os números.

**Critérios de aceite:**
- [ ] O email de notificação enviado ao gestor inclui a narrativa completa do time no corpo da mensagem (não apenas um link genérico)
- [ ] No relatório acessado dentro do Kanvas, a seção de narrativa aparece acima dos dados automáticos, com o mesmo destaque visual que o líder viu ao preencher
- [ ] O gestor acessa o relatório de qualquer time que ele supervisiona em até 2 cliques a partir da tela principal
- [ ] O relatório indica claramente quem preencheu e quando foi enviado

**Onda:** MVP

---

### US-05 — Consultar histórico de relatórios anteriores como referência

Como líder de time que preenche o relatório toda semana, quero ver meus relatórios anteriores sem sair da tela de preenchimento, para que eu consiga manter consistência e não precisar lembrar o que já foi comunicado ao gestor.

**Critérios de aceite:**
- [ ] O histórico dos últimos 8 relatórios está acessível a partir da tela de preenchimento sem recarregar a página
- [ ] Cada entrada do histórico mostra: data, sprint associada, status (enviado / rascunho)
- [ ] O líder consegue abrir qualquer relatório anterior para leitura completa em até 2 cliques
- [ ] Relatórios com status "rascunho" estão visualmente diferenciados dos enviados

**Onda:** 2
