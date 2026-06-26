# Análise de Concorrentes — Relatórios e Visibilidade de Progresso
**Escopo:** Como os principais players abordam relatórios de progresso e visibilidade para gestores
**Data:** Junho 2026

---

## Asana

**Abordagem:** Goals e Status Updates — gestores definem objetivos, times atualizam status manualmente.

**Como funciona na prática:**
- O responsável por um projeto pode publicar um "Status Update" com texto livre, indicador de saúde (verde/amarelo/vermelho) e progresso percentual.
- Não é automático — alguém precisa escrever o update toda semana.
- Gestores recebem digest por email com os updates publicados.

**Feedback dos usuários (G2, Capterra — compilado):**
- "Fica desatualizado rapidamente. Ninguém lembra de publicar o update na sexta."
- "A pessoa que deveria postar o status está sempre ocupada com o trabalho real."
- "Quando lembro de atualizar, fico 20 minutos tentando decidir o que colocar."
- Avaliação média da feature de reports: 3,4/5

**Relevância para o case Kanvas:** Asana tem o mesmo problema estrutural — a pessoa
que se beneficia do relatório não é quem faz o trabalho de produzi-lo. A solução
deles (text free + indicador) dá mais flexibilidade mas não resolve o esforço.

---

## Monday.com

**Abordagem:** "Updates" — posts de progresso publicados por membros do time, visíveis para todos no projeto.

**Como funciona na prática:**
- Qualquer membro pode postar um update com texto, arquivos e menções.
- Updates ficam numa timeline do projeto — gestores podem acompanhar sem precisar perguntar.
- Recentemente lançaram "AI Summary" que tenta sumarizar os updates automaticamente.

**Diferencial relevante:** os updates são publicados por quem tem o contexto — não
há formulário fechado. A pessoa escolhe o que compartilhar e como.

**Fraqueza:** sem estrutura, os updates ficam inconsistentes. Times diferentes
publicam em formatos diferentes. Gestor precisa interpretar muito.

**Relevância para o case Kanvas:** Monday.com validou que dar agência ao time
funciona melhor do que formulário fechado preenchido a contragosto. Mas trocou
consistência por liberdade.

---

## Notion

**Abordagem:** não é uma ferramenta de gestão de projetos com reports nativos — mas é a alternativa para a qual os usuários mais migram quando abandonam ferramentas como Kanvas.

**Por que as pessoas migram para o Notion:**
- Criam templates próprios de weekly update com os campos que fazem sentido para o contexto deles.
- Cada time pode adicionar campos de contexto que o sistema original não permitia.
- Gestores e times compartilham o mesmo documento — não há separação entre quem escreve e quem lê.

**Fraqueza:** trabalho manual de criar e manter os templates. Sem automação de envio.

**O que isso revela:** quando as pessoas migram para o Notion para fazer algo que
a ferramenta original deveria fazer, o problema raramente é de funcionalidade.
É de controle e contexto.

---

## Linear

**Abordagem:** excelente tracking de tasks e cycles, mas sem camada de relatório para gestores.

**Relevância para o case Kanvas:** Linear é referência de produto bem feito para
times de desenvolvimento. A ausência proposital de relatórios para gestores é uma
decisão de produto — eles focaram nos que executam, não nos que supervisionam.
Serve de contraste: o que acontece quando você otimiza apenas para quem faz o trabalho.

---

## Síntese competitiva

| Player | Quem preenche | Formato | Contexto | Automação |
|--------|--------------|---------|----------|-----------|
| Kanvas | Líder de time (forçado) | Formulário fechado | Não | Sim |
| Asana | Líder de time (voluntário) | Text livre + indicador | Sim | Não |
| Monday.com | Qualquer membro (voluntário) | Post livre | Sim | Parcial (AI) |
| Notion | Qualquer membro (manual) | Template customizável | Sim | Não |

**Gap não resolvido por nenhum player:** nenhum combina automação com narrativa
controlada pelo time. Kanvas tem automação mas sem narrativa. Monday/Notion têm
narrativa mas sem automação consistente.

Quem resolver "relatório automático com narrativa editável pelo time" antes dos
concorrentes tem uma vantagem defensável no segmento mid-market.
