# Padrões — Research Stage 2

## Padrões identificados

---

### Padrão 1: Narrativa do time é invisível — dados automáticos sobrepõem contexto

O sistema gera dados (velocidade, tickets, percentual de conclusão) e os posiciona como o conteúdo principal do relatório. O espaço para o líder de time explicar o que aconteceu de verdade é pequeno, escondido e tratado como detalhe — quando existe. O resultado é que o relatório frequentemente conta a história errada.

**Fontes:**
- Rafael Santos: sprint "lenta" porque liderou resposta a incidente em produção — dado mostrou queda de 30% de velocidade sem contexto. Campo de texto "pequenininho e escondido"
- Carla Mendes: coordenador disse "o relatório não me representa — não é o que aconteceu de verdade na semana"
- Thiago Lima: "o sistema capturava velocidade mas não capturava contexto"
- Fernanda Rocha: 3 dias salvando maior cliente apareceram como "3 tickets resolvidos e 2 QBRs"
- Marcos Carvalho: "75% de conclusão sem contexto parece que a gente foi lenta. Mas priorizamos bugs críticos — foi uma decisão boa"
- Lucas Pereira: "no Kanvas eu preencho o que o sistema quer saber. No Slack eu conto o que aconteceu"
- Isabela Costa: "o problema é de quem conta a história. Hoje o sistema conta. E o sistema não sabe o contexto"
- Analytics: 21% dos tickets de suporte são "quero adicionar mais informações mas não tem campo"
- Competitivo: nenhum player combina automação com narrativa controlada pelo time — gap de mercado identificado

**Confirmação quantitativa:** `report_configured` -37,9% + NPS líderes de time -8 confirmam que o produtor do conteúdo está largando a feature. `report_viewed` caiu apenas -10,6% — os gestores ainda tentam ler, mas o conteúdo não está lá.

**Hipótese de causa raiz:** O relatório foi arquitetado com dados automáticos como protagonistas e narrativa como rodapé. Se o líder de time não consegue contar o que aconteceu antes dos números chegarem ao gestor, ele percebe que o relatório o representa mal — e para de preencher com qualidade ou inteiramente.

---

### Padrão 2: Feedback loop ausente destrói a motivação ao longo do tempo

Líderes de time que preenchem relatórios regularmente nunca recebem nenhuma reação do gestor — nenhum comentário, pergunta sobre bloqueio mencionado, ou reconhecimento de esforço. A ausência de resposta faz o preenchimento parecer burocracia sem propósito, e a motivação decai progressivamente.

**Fontes:**
- Marcos Carvalho: testou 4 semanas com preenchimento cada vez mais vazio — levou 1 mês até alguém notar. "Quando o relatório vai pra um lugar onde ninguém reage, parece burocracia"
- Thiago Lima: "CEO parou de abrir porque não tinha informação útil. Líderes perceberam que ninguém lia e pararam de se esforçar. Virou um ciclo"
- Fernanda Rocha: "o relatório fica ruim, o gestor para de ler, a gente percebe que ninguém lê e para de se esforçar" — descreveu o ciclo com precisão
- Sofia Andrade: líder de time disse que "não entende pra que serve o relatório se nunca recebe nenhum retorno"
- Sofia Andrade (auto-crítica): "Deveria dar mais feedback quando leio os relatórios. Mas o produto deveria facilitar esse loop, não depender de eu lembrar"
- Lucas Pereira: no Slack a diretora deixa reações toda segunda. "Loop de feedback que simplesmente não existia antes"

**Confirmação quantitativa:** `report_viewed` -10,6% (gestores ainda abrem) vs `report_configured` -37,9% (líderes estão parando de preencher). A assimetria sugere que gestores ainda tentam consumir mas líderes já desistiram — consistente com ciclo de desmotivação progressiva.

**Hipótese de causa raiz:** O produto não oferece nenhum mecanismo de resposta do gestor para o líder de time. Sem feedback visível, preencher um relatório é um ato unilateral sem retorno, e comportamentos sem reforço positivo tendem a ser abandonados.

---

### Padrão 3: Times constroem processos paralelos fora do sistema — workaround generalizado

Quando o formato do Kanvas não permite expressar o contexto real do trabalho, líderes e gestores criam processos alternativos — mais trabalhosos, mas que entregam o que o sistema não entrega. A disposição para trabalhar existe; o problema é que o esforço está acontecendo fora do produto.

**Fontes:**
- Rafael Santos: exporta para planilha + email manual toda sexta. Gestora parou de abrir o Kanvas e passa a depender do email
- Bruno Alves: WhatsApp na quinta + síntese manual de 25-30 min + repreenche Kanvas. "Sou o tradutor — o sistema pega os dados do projeto mas não pega o contexto"
- Carla Mendes / Thiago Lima: migraram para planilha + Notion e Notion respectivamente com templates customizáveis
- Marina Oliveira: voltou à reunião semanal de 45 min — exatamente o formato que o Kanvas prometia eliminar
- Lucas Pereira: canal #weekly-update no Slack com template estruturado, diretora lê e dá feedback. "Seria ideal ter os dois: dados automáticos mais narrativa"
- Analytics: `report_exported_csv` +214,7% — comportamento de workaround é sistêmico, não individual

**Confirmação quantitativa:** crescimento de +214,7% em exportação CSV é o sinal mais claro: usuários estão extraindo os dados do Kanvas para construir seu próprio artefato de comunicação. Contas que cancelaram têm 4,2 eventos de export CSV/mês vs 0,8 das ativas — workaround é preditor de churn.

**Hipótese de causa raiz:** A lacuna entre o que o sistema produz automaticamente e o que o líder de time precisa comunicar é real e urgente. Usuários dispostos a criar processos paralelos trabalhosos demonstram que a motivação para comunicar existe — o que falta é o formato adequado dentro do produto.

---

### Padrão 4: Design assimétrico — produto otimizado para o leitor, não para o escritor

O produto foi desenhado tendo o gestor (consumidor do relatório) como usuário primário, mas quem decide se o produto funciona é o líder de time (produtor). Quando o produtor abandona o produto, o consumidor perde o que lia — e o ciclo colapsa.

**Fontes:**
- Carla Mendes: "O produto foi desenhado pra quem lê o relatório, não pra quem escreve. E quem escreve é quem define se o produto funciona ou não"
- Sofia Andrade: "O produto não foi projetado para quem vai alimentar ele. Foi projetado para quem vai ler. Se o produto ignora a experiência de quem alimenta, quem alimenta para de usar"
- Lucas Pereira: "A ideia foi pensada do ponto de vista de quem recebe, não de quem produz"
- Marcos Carvalho: "O produto me trata como um coletor de dado, não como alguém com perspectiva"
- Isabela Costa: "nos casos em que funciona mal, sempre tem uma divisão: uma pessoa que se beneficia da visibilidade e outra que precisa fazer o trabalho de gerar essa visibilidade. São motivações completamente diferentes"
- Analytics: NPS gestores +34 vs líderes de time -8 — satisfação bifurcada confirma a assimetria de experiência

**Confirmação quantitativa:** NPS líderes -8 vs gestores +34 — diferença de 42 pontos. Churn concentrado em mid-market (segmento com maior separação estrutural entre quem sabe e quem precisa do relatório). Líderes de time -31% em uso vs gestores -5,7%.

**Hipótese de causa raiz:** O design priorizou a experiência de receber informação em detrimento da experiência de produzir. Em qualquer produto onde o consumidor e o produtor são pessoas diferentes, ignorar a experiência do produtor é um risco estrutural — ele é quem decide, na prática, se o produto tem conteúdo.

---

## Sinais fracos (menos de 3 fontes)

- **Medo de avaliação negativa pelos números** — líderes sentem que relatórios ruins os prejudicam mesmo quando o contexto justifica. Fontes: Isabela (via colega), Sofia (via líder direta) — 2 fontes qualitativas indiretas
- **Empresa small (< 50) e enterprise (500+) menos afetadas** — queda de apenas -11 a -12% vs -38 a -44% no mid-market. Fonte única: analytics. Hipótese: nesses segmentos, quem sabe e quem preenche tendem a ser a mesma pessoa (como Isabela)
- **Tickets "como preencher" são 38% do suporte** — pode indicar problema de onboarding ou UX, mas sem entrevistas específicas sobre esse perfil é difícil separar de dificuldade com o próprio formato

---

## Ranking de hipóteses

| # | Hipótese | Fontes | Confirmação quantitativa | Relação com churn |
|---|----------|--------|--------------------------|-------------------|
| 1 | O relatório representa mal o trabalho do time porque dados automáticos sobrepõem contexto narrativo — desincentivando o preenchimento | 9 fontes (7 entrev. + analytics + competitivo) | `report_configured` -37,9%, NPS líderes -8, 21% tickets sobre "campos insuficientes" | **Direta** — líder para de preencher → gestor perde visibilidade → churn |
| 2 | O design otimizou para o leitor (gestor) ao custo do escritor (líder de time), criando assimetria estrutural | 6 fontes (5 entrev. + analytics) | NPS gap de 42 pontos, queda assimétrica no uso (-31% líderes vs -5,7% gestores) | **Direta** — é a causa raiz do padrão 1 |
| 3 | Ausência de feedback loop do gestor para o líder transforma o preenchimento em burocracia sem propósito | 6 fontes (5 entrev. + analytics) | Assimetria `report_viewed` -10,6% vs `report_configured` -37,9% | **Indireta** — amplifica o abandono mas não é a causa inicial |
| 4 | Usuários criam workarounds porque a disposição de comunicar existe — o formato é que está errado | 6 fontes (5 entrev. + analytics) | `report_exported_csv` +214,7%, export CSV prediz churn | **Sinal** — confirma que o problema não é motivação, é produto |

**Nota de síntese:** os padrões 1 e 2 são dois lados do mesmo problema: o produto foi desenhado tendo como usuário central o gestor que recebe, não o líder que produz. A hipótese central é que inverter essa lógica de design — dar ao líder de time controle sobre a narrativa antes que os dados automáticos cheguem ao gestor — resolve simultaneamente a representação inadequada do trabalho e o ciclo de abandono.
