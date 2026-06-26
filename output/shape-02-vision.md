# Visão de Produto — Kanvas Relatório Contextual

## Visão

Para líderes de time em empresas de médio porte que precisam reportar progresso
sem que o relatório distorça o que realmente aconteceu na semana, o **Relatório
Contextual** é uma reformulação da experiência de preenchimento semanal que
coloca a narrativa do time antes dos dados automáticos — e fecha o loop com
uma resposta visível do gestor.

## É / Não é

| É | Não é |
|---|-------|
| Uma reformulação da experiência de preenchimento do relatório existente | Uma reescrita do mecanismo de coleta automática de dados |
| Uma solução centrada no produtor do relatório (líder de time) | Uma solução primariamente para o consumidor (gestor) |
| Uma mudança de hierarquia: narrativa primeiro, dados automáticos como complemento | Um formulário com mais campos obrigatórios |
| Um MVP incremental dentro da feature existente | Um produto novo ou módulo separado |
| Um loop de feedback fechado entre quem produz e quem consome | Um sistema de aprovação ou moderação de relatórios |

## Faz / Não faz

| Faz | Não faz |
|-----|---------|
| Exibe campo de narrativa proeminente (texto livre, sem limite artificial) como ponto central do relatório | Substitui os dados automáticos — eles continuam sendo gerados e exibidos |
| Oferece template leve de 3 seções como guia (o que foi feito / o que ficou travado / o que precisa de atenção) | Permite customização de template por empresa no MVP |
| Notifica o líder de time quando o gestor abre e reage ao relatório | Gera analytics sobre o conteúdo das narrativas |
| Posiciona os dados automáticos como complemento da narrativa, não como cabeçalho | Integra com ferramentas externas (Slack, Notion, email) no MVP |
| Permite ao gestor reagir ao relatório com comentário ou reação rápida | Cria fluxo de aprovação antes do envio do relatório |

## Usuário-alvo

**Primário:** Líder de time (tech lead, CS lead, gerente de área) em empresa
de 50–300 funcionários, que preenche o relatório semanalmente e reporta para
um gestor que não acompanha o dia a dia operacional. Seu trabalho tem
componentes contextuais e qualitativos que não se traduzem bem em métricas
de velocidade ou tickets resolvidos.

**Secundário:** Gestor (head, VP, COO, CTO) que recebe o relatório. Não está
abandonando a feature, mas perde valor porque o insumo que recebe é cada vez
mais raso. A solução restaura o valor para ele como consequência de resolver
o problema do produtor.

## Métricas de sucesso

1. **Taxa de relatórios enviados no prazo** sobe de 52% para ≥70% em 60 dias
   após o lançamento — medido via `report_configured` dividido pelo total de
   relatórios esperados no período.

2. **NPS de líderes de time** sobe de -8 para ≥+15 no trimestre seguinte ao
   lançamento — medido via pesquisa NPS segmentada por perfil.

3. **Churn mid-market** cai de 6,8% para ≤4,5% ao mês em 90 dias após o
   lançamento — medido via dados de cancelamento segmentados por tamanho de
   empresa (50–300 funcionários).
