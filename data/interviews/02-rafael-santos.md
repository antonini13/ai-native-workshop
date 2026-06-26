# Entrevista 02 — Rafael Santos
**Cargo:** Tech Lead
**Empresa:** Startup de fintech, 80 funcionários
**Perfil:** Líder de time — preenche (ou deveria preencher) os relatórios
**Data:** 04/06/2026

---

**Pesquisador:** Rafael, você pode me contar como é a sua relação com a
feature de Relatórios Automáticos do Kanvas?

**Rafael:** Olha, eu vou ser honesto com você porque acho que isso precisa
chegar pra alguém. Eu parei de usar. Não completamente, mas... praticamente.

**Pesquisador:** Me conta o que aconteceu.

**Rafael:** A gente tem sprint de duas semanas. No final de cada sprint eu
precisava preencher o relatório — progresso, o que entregamos, o que ficou
pra trás, bloqueios. No começo eu fazia direitinho. Levava uns 8, 10 minutos.

Só que o negócio é assim: o sistema pega os dados automaticamente — quantos
tickets foram resolvidos, velocidade do sprint, esse tipo de coisa. Mas aí
ele mostra esses números pro meu gestor sem contexto nenhum. Uma semana a
gente entregou 4 tickets e o sistema mostrou que a velocidade caiu 30% em
relação à sprint anterior. Meu gestor me chamou pra perguntar o que tinha
acontecido.

**Pesquisador:** E o que tinha acontecido?

**Rafael:** A gente passou dois dias lidando com um incidente em produção que
não tinha nada a ver com o nosso sprint. Sistema de terceiro que caiu,
afetou a API de pagamento do nosso maior cliente. A gente teve que parar tudo
e resolver. Depois disso o sprint ficou curtinho mesmo.

Só que o relatório não tinha esse contexto. Mostrava os números, ponto. E aí
parece que meu time foi lento. Isso me irritou muito.

**Pesquisador:** E você não colocou esse contexto no relatório?

**Rafael:** Tentei. Mas o campo de texto livre é pequenininho, tipo 3 linhas,
e fica escondido embaixo de um monte de campo obrigatório de percentual. Fica
parecendo nota de rodapé. Não é o destaque — o destaque são os números.

Depois disso eu comecei a exportar os dados do Kanvas pra uma planilha e
mando um email pra minha gestora toda sexta com o resumo. Eu escrevo o que
aconteceu de verdade, o contexto, o que precisa de atenção. Ela disse que
prefere assim.

**Pesquisador:** E o relatório do Kanvas?

**Rafael:** Eu preencho o mínimo. Às vezes nem isso. Não faz diferença porque
ela nem abre mais — sabe que vai ter o email.

**Pesquisador:** Se você fosse redesenhar essa feature, como seria?

**Rafael:** Cara, eu queria poder contar o que aconteceu na semana do ponto
de vista do time antes de os números chegarem pro gestor. Tipo, eu escrevo o
contexto primeiro, depois vem o dado. Não o contrário. Porque número sem
contexto é quase pior do que nenhum número.
