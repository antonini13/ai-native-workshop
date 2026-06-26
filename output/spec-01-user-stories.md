# User Stories — Relatório Contextual Kanvas

## Jornadas identificadas

1. Líder de time preenche a narrativa semanal e envia o relatório
2. Líder de time confirma que o gestor viu e respondeu
3. Gestor lê o relatório com narrativa em primeiro plano
4. Gestor reage e fecha o loop com o produtor
5. Dados automáticos complementam a narrativa sem substituí-la

---

## Stories

### US-01 — Campo de narrativa como elemento central do relatório

Como líder de time, quero um campo de texto amplo e estruturado em 3 seções
ocupando o centro da tela de preenchimento do relatório, para que eu possa
contar a história da semana com a minha voz antes de os dados automáticos
chegarem ao gestor.

**Critérios de aceite:**
- [ ] A tela de preenchimento exibe 3 campos de texto livre em sequência: "O que foi feito", "O que ficou travado", "O que precisa de atenção da liderança"
- [ ] Cada campo tem altura mínima de 4 linhas com redimensionamento vertical livre e sem limite de caracteres visível
- [ ] Os campos de narrativa ocupam ao menos 55% da largura da tela em viewport desktop (≥1280px)
- [ ] O conteúdo dos campos é salvo automaticamente como rascunho a cada 30 segundos enquanto o usuário digita
- [ ] Um rascunho salvo é restaurado automaticamente se o usuário fechar e reabrir a tela antes de enviar

**Onda:** MVP

---

### US-02 — Dados automáticos posicionados como complemento da narrativa

Como líder de time, quero que os dados automáticos do sprint apareçam em
posição visualmente secundária em relação à minha narrativa, para que o gestor
não interprete os números antes de entender o contexto do que aconteceu.

**Critérios de aceite:**
- [ ] Os dados automáticos (velocidade, tickets resolvidos, progresso percentual) são exibidos em sidebar ou seção abaixo da narrativa — nunca acima ou como elemento de destaque
- [ ] O componente de dados tem label explícita "Dados automáticos" acompanhada de ícone de informação com tooltip "Coletados automaticamente do projeto"
- [ ] O tamanho dos cards de dados é visivelmente menor que os campos de narrativa (diferença de hierarquia tipográfica e área)
- [ ] Os dados são populados automaticamente sem nenhuma ação do líder de time

**Onda:** MVP

---

### US-03 — Envio do relatório e confirmação de status

Como líder de time, quero enviar o relatório com um clique e ver o status de
leitura do gestor, para que eu saiba que o que escrevi foi entregue e recebido.

**Critérios de aceite:**
- [ ] O botão "Enviar relatório" está habilitado se ao menos um dos 3 campos de narrativa tiver conteúdo
- [ ] Após o envio, o status do relatório muda para "Enviado" e uma confirmação visual é exibida
- [ ] A tela de preenchimento da semana seguinte exibe o indicador do relatório anterior: "Enviado em [data] — lido por [nome do gestor] ✓" ou "Enviado em [data] — ainda não lido"
- [ ] O status de leitura é atualizado em tempo real ou no próximo carregamento da tela (sem necessidade de refresh manual)

**Onda:** MVP

---

### US-04 — Leitura do relatório pelo gestor com narrativa em primeiro plano

Como gestor, quero ver a narrativa do líder de time como primeiro elemento
da tela de leitura do relatório, para que eu entenda o que aconteceu de verdade
na semana antes de olhar para os números.

**Critérios de aceite:**
- [ ] A tela de leitura exibe os 3 blocos de narrativa (O que foi feito / O que ficou travado / O que precisa de atenção) como conteúdo principal, em texto corrido — não em campos de formulário
- [ ] Os dados automáticos aparecem em sidebar ou seção secundária visualmente subordinada à narrativa
- [ ] O header do relatório identifica claramente quem enviou, de qual time, e em qual data
- [ ] Ao abrir o relatório, o status de leitura do lado do líder de time é atualizado para "lido"

**Onda:** MVP

---

### US-05 — Reação e comentário do gestor

Como gestor, quero reagir ao relatório com uma reação rápida ou comentário
de texto, para que o time saiba que fui informado e o que farei com a informação.

**Critérios de aceite:**
- [ ] A tela de leitura do gestor exibe 3 botões de reação rápida: "Entendido", "Quero conversar", "Tomei uma ação"
- [ ] O gestor pode adicionar um comentário de texto livre (campo sem limite de caracteres) junto com ou sem uma reação rápida
- [ ] Após enviar a reação/comentário, o líder de time recebe uma notificação in-app
- [ ] A reação e o comentário ficam visíveis no histórico do relatório para ambos os lados

**Onda:** MVP

---

### US-06 — Notificações por e-mail para fechamento do loop

Como líder de time, quero receber um e-mail quando meu gestor reagir ao
relatório que enviei, para que eu seja informado mesmo quando não estou com
o Kanvas aberto.

**Critérios de aceite:**
- [ ] Um e-mail é enviado ao líder de time quando o gestor deixa reação ou comentário em seu relatório
- [ ] O e-mail inclui o nome do gestor, o tipo de reação, o trecho do comentário (se houver), e um link direto para o relatório
- [ ] O líder pode desativar notificações de e-mail desta feature nas configurações de conta
- [ ] O e-mail é enviado em até 5 minutos após a ação do gestor

**Onda:** Onda 2 — notificação in-app (US-05) é suficiente para validar o loop no MVP; e-mail adiciona cobertura mas não muda a hipótese core
