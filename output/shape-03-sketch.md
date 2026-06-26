# Sketch de Interface — Relatório Contextual

## Sketch gerado com Lovable

Preview: https://id-preview--8d9a3848-e3f7-4a8d-8cff-a6a3a53b99d6.lovable.app
Editor: https://lovable.dev/projects/8d9a3848-e3f7-4a8d-8cff-a6a3a53b99d6

---

### O que foi construído

Duas telas com navegação entre elas, construídas em React + shadcn/ui, com
layout 5 colunas (3/2) que coloca a narrativa como protagonista e os dados
automáticos como elemento de suporte na sidebar.

---

### Tela 1 — Preenchimento do relatório (rota `/`)

A tela do líder de time. A inversão de hierarquia é visível imediatamente:
a narrativa ocupa 60% do espaço (3/5 colunas), os dados ficam na sidebar
direita (2/5 colunas) em cards menores e com menor peso visual.

**Componentes:**
- Header com nome do projeto, período e badge "Pendente de envio"
- Seção "O que aconteceu esta semana" — título em 20px, subtítulo orientativo
- 3 campos `NarrativeField` com altura mínima de 32 linhas e resize vertical:
  - "O que foi feito"
  - "O que ficou travado"
  - "O que precisa de atenção da liderança"
- Sidebar com label "Dados automáticos desta semana" + ícone de info com tooltip
- 3 `MetricCard` compactos: Velocidade (18 pts, -25% em vermelho), Tickets (7), Progresso (68%)
- Footer: "Salvar rascunho" (link) + "Enviar relatório" (botão primário slate-900)
- Indicador: "Último relatório enviado: 13 Jun — lido por Ana Rodrigues ✓"

---

### Tela 2 — Leitura do relatório (rota `/report`)

A tela do gestor. A narrativa preenchida pelo líder é exibida como texto
corrido, sem campos de formulário — o gestor lê, não preenche.

**Componentes:**
- Header com nome do time, quem enviou, data e badge "Lido"
- Narrativa em 3 blocos: label em caps pequenos, texto em 16px line-relaxed
- Seção "Sua resposta" com:
  - Campo de texto livre (textarea)
  - 3 botões de reação rápida em pill: 👍 Entendido | ⚠️ Quero conversar | ✅ Tomei uma ação
  - Botão "Enviar resposta" + nota "Rafael Santos será notificado quando você responder"
- Mesma sidebar de dados com nota contextual: "Velocidade -25% — contexto: incidente em produção na segunda e terça"
