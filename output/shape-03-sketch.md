# Sketch — Shape Stage 3

## Tela principal: Weekly Update (preenchimento pelo líder de time)

**Justificativa:** esta é a tela do momento crítico identificado no Research — sexta-feira, o líder de time vai preencher o relatório semanal. É aqui que o produto hoje falha (formulário com campos de percentual em destaque, narrativa como rodapé) e onde a mudança de design tem maior impacto imediato. Se essa tela funcionar, o ciclo inteiro se recupera.

---

## Prompt para geração manual de interface

Cole este prompt no Lovable (lovable.dev), v0 (v0.dev), ou ferramenta similar:

---

Crie a interface de uma aplicação SaaS de gestão de projetos chamada Kanvas. Estou construindo a tela de preenchimento de atualização semanal de times — chamada "Weekly Update". Essa é a tela que um líder de time (tech lead, coordenador, manager) usa toda semana para reportar o que aconteceu para o seu gestor.

**Contexto do produto:**
O Kanvas é um SaaS de gestão de projetos para times de 50 a 300 funcionários. O problema que estamos resolvendo: o sistema atual exibe métricas automáticas (velocidade, tickets resolvidos, percentual de conclusão) como conteúdo principal do relatório, deixando a narrativa do time como detalhe secundário. O resultado é que os líderes de time sentem que o relatório os representa mal — e param de preencher. A solução é inverter a hierarquia: narrativa do time em primeiro lugar, dados automáticos como contexto de apoio abaixo.

**Layout geral:**
- Sidebar esquerda fixa com navegação principal do produto
- Área principal central com a tela de preenchimento
- Sem modais, sem drawers — tudo na mesma página

**Sidebar esquerda:**
- Fundo: #111827 (cinza muito escuro)
- Logo "Kanvas" no topo (texto branco, fonte Inter bold)
- Itens de navegação: Dashboard, Projetos, Relatórios (ativo), Time, Configurações
- Item ativo com fundo levemente mais claro (#1F2937) e ícone em azul (#2563EB)
- Ícones simples, linha fina (estilo Lucide ou Heroicons)
- Na base da sidebar: avatar do usuário logado (foto circular placeholder) + nome "Rafael Santos" + cargo "Tech Lead"

**Área principal — tela "Weekly Update":**

Header da página:
- Título: "Atualização semanal" em texto grande (24px, font-semibold, cinza escuro #111827)
- Subtítulo: "Sprint 24 · 17 a 23 de junho de 2026" em cinza médio (#6B7280, 14px)
- Badge de status à direita do título: "Rascunho" em amarelo suave (#FEF3C7, texto #92400E)
- Botão primário no canto superior direito: "Enviar relatório" (azul #2563EB, texto branco, border-radius 6px)
- Botão secundário ao lado: "Salvar rascunho" (borda cinza, fundo branco)

Seção 1 — Narrativa do time (DESTAQUE PRINCIPAL):
- Label em cima: "Narrativa da semana" em uppercase, letter-spacing, cinza médio (#6B7280, 12px)
- Três cards brancos empilhados verticalmente, com borda fina (#E5E7EB), border-radius 8px, padding 16px
- Card 1: label "O que aconteceu esta semana" (font-medium, #374151) + textarea grande (mínimo 100px de altura) com placeholder em cinza claro "Descreva o que o time fez, o que foi entregue, decisões tomadas..." — este campo está preenchido com texto de exemplo: "Concluímos a integração com o gateway de pagamento Stripe após dois dias de debugging intenso. Identificamos e corrigimos um bug de concorrência que afetava transações simultâneas — estava fora do escopo original mas era crítico para o lançamento."
- Card 2: label "O que ficou para trás" + textarea com placeholder "O que não foi entregue e por quê..." — preenchido com: "A tela de relatório financeiro foi adiada. Dependíamos da API do time de dados que teve um incidente na quarta."
- Card 3: label "O que precisa de atenção da liderança" + textarea com placeholder "Bloqueios, riscos, decisões que precisam de você..." + badge "Opcional" em cinza suave à direita do label — preenchido com: "Precisamos de acesso ao ambiente de staging do cliente para os testes de aceitação na próxima semana."

Seção 2 — Dados do projeto (CONTEXTO DE APOIO, visualmente secundário):
- Separador com label centralizado: "Dados automáticos do projeto" em cinza claro (#9CA3AF, 12px, uppercase) com linha horizontal em cada lado
- Três metric cards em linha (grid de 3 colunas), fundo cinza muito claro (#F9FAFB), borda fina (#E5E7EB), border-radius 8px, padding 12px
- Metric 1: label "Velocidade" (cinza, 12px) + número grande "18" (28px, #111827) + subtexto "pts nesta sprint" (cinza, 12px) + tag "+12% vs sprint anterior" em verde suave (#D1FAE5, texto #065F46)
- Metric 2: label "Tickets resolvidos" + número grande "12" + subtexto "de 15 planejados" + barra de progresso fina abaixo (80% preenchida, azul #2563EB sobre cinza #E5E7EB)
- Metric 3: label "Status geral" + indicador grande (círculo 24px verde #10B981) + texto "No prazo" em #111827 + subtexto "última atualização: hoje"

Rodapé da tela:
- Linha separadora
- Texto à esquerda: "Este relatório será enviado para Marina Oliveira (Head of Projects)" em cinza #6B7280, 14px
- Botão "Enviar relatório" repetido (mesmo estilo do header) à direita

**Direção visual obrigatória:**
- Use Tailwind CSS e shadcn/ui
- Estilo inspirado no Linear: limpo, sem sombras pesadas, sem gradientes, sem ilustrações decorativas
- Fundo da área principal: branco #FFFFFF
- Tipografia: Inter (ou sistema sans-serif como fallback)
- Cor de ação principal: azul #2563EB
- Bordas de card: #E5E7EB, espessura 1px
- Density confortável — não compactar demais
- Parecer um produto B2B real, não um template genérico
- Não use dados reais de usuários — use os dados fictícios de exemplo definidos acima

**O que NÃO fazer:**
- Não adicionar IA generativa, sugestões automáticas ou botões "gerar com IA"
- Não usar sombras box-shadow pesadas
- Não usar gradientes ou cores vibrantes além do azul de ação
- Não criar modais ou sidebars deslizantes
- Não colocar os dados automáticos antes da narrativa do time

---

### Componentes principais

| Componente | Propósito |
|------------|-----------|
| Sidebar de navegação | Contexto do produto — não é o foco desta tela |
| Header com status e ações | Deixa claro que é um rascunho e onde está o botão de envio |
| Cards de narrativa (3 campos) | **Core da solução** — onde o líder de time conta o que aconteceu |
| Separador visual antes dos dados | Sinal visual de que dados são contexto, não destaque |
| Metric cards (dados automáticos) | Contexto de apoio — visualmente subordinados à narrativa |
| Footer com destinatário | Reforça que o relatório vai para alguém real — incentiva qualidade |
