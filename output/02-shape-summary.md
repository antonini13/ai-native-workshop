# Shape Summary — Stage 2

## Oportunidade

Líderes de time em empresas de 50–300 funcionários têm contexto real e motivação para comunicar o que acontece no seu trabalho — o problema é que o formato atual do Kanvas os trata como coletores de dados, posicionando métricas automáticas como protagonistas e narrativa como nota de rodapé. Para contornar isso, esses usuários constroem sistemas paralelos (email, Slack, WhatsApp) mais trabalhosos e sem integração com o sistema de gestão. A oportunidade é permitir que o líder de time conte o que aconteceu na semana antes dos dados automáticos chegarem ao gestor — tornando o relatório um artefato que representa o trabalho de verdade e devolvendo ao produto o papel central no fluxo de visibilidade que ele prometia ter.

## Visão

**Para líderes de time que precisam reportar progresso para gestores que não acompanham o trabalho diário, o Kanvas Weekly é uma atualização semanal estruturada que coloca a narrativa do time em primeiro lugar — com os dados automáticos do projeto como contexto, não como protagonistas.**

| É | Não é |
|---|-------|
| Espaço para o líder contar o que aconteceu antes dos dados chegarem | Avaliação de performance ou prestação de contas individual |
| Complemento à automação de dados já existente | Substituto para boards, sprints ou tasks |
| Atualização semanal com estrutura fixa (narrativa + dados) | Mensageiro de equipe ou ferramenta de comunicação geral |
| Solução para o ciclo de abandono por má representação | Reescrita completa da feature atual |
| Parte do fluxo existente do Kanvas | Sistema de templates customizáveis por time |

| Faz | Não faz |
|-----|---------|
| Abre o preenchimento com campo de narrativa em destaque | Processa texto com IA para sugestões automáticas (v1) |
| Monta relatório: narrativa do time → dados automáticos | Permite campos customizáveis por time (v1) |
| Notifica gestor quando o relatório fica disponível | Loop de feedback do gestor para o líder (v1 — adiado) |
| Mantém histórico de relatórios anteriores acessível | Integra com ferramentas externas como Slack ou email |

## Sketch

Lovable não estava disponível no ambiente. O prompt completo e auto-suficiente para geração da interface está em `output/shape-03-sketch.md` — pode ser colado diretamente em Lovable (lovable.dev) ou v0 (v0.dev).

**Tela principal:** Weekly Update — tela de preenchimento pelo líder de time, com narrativa em destaque (3 campos: o que aconteceu, o que ficou para trás, o que precisa de atenção) e dados automáticos do projeto abaixo como contexto de apoio.

## Métricas de sucesso

1. `report_configured` volta ao baseline de Janeiro (8.000+ eventos/mês) — analytics, avaliado 90 dias pós-lançamento
2. Taxa de relatórios enviados no prazo sobe de 52% para 70%+ — analytics, meta em 60 dias
3. Churn mid-market (50–300 func.) cai abaixo de 4% (de 6,8%) — CRM, avaliado no quarter seguinte
