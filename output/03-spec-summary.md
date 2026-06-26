# Spec Summary — Relatório Contextual Kanvas

## O problema resolvido

Líderes de time no mid-market não preenchem os Relatórios Automáticos do Kanvas
com qualidade porque o formato atual os posiciona como coletores de dados
numéricos — não como narradores do que realmente aconteceu — tornando o
preenchimento um risco perceptivo sem retorno visível.

## A aposta

Para líderes de time em empresas de médio porte que precisam reportar progresso
sem que o relatório distorça o que realmente aconteceu na semana, o **Relatório
Contextual** coloca a narrativa do time antes dos dados automáticos — e fecha
o loop com uma resposta visível do gestor.

## Tasks criadas no Linear — Onda 1 (MVP)

| Story | Título | Tamanho | Link |
|-------|--------|---------|------|
| US-01 | Campo de narrativa como elemento central | M | https://linear.app/antonini-portfolio/issue/ANT-207 |
| US-02 | Dados automáticos como complemento visual | P | https://linear.app/antonini-portfolio/issue/ANT-208 |
| US-03 | Envio e indicador de status de leitura | M | https://linear.app/antonini-portfolio/issue/ANT-209 |
| US-04 | Leitura pelo gestor com narrativa em destaque | M | https://linear.app/antonini-portfolio/issue/ANT-210 |
| US-05 | Reação e comentário do gestor | M | https://linear.app/antonini-portfolio/issue/ANT-211 |

**Estimativa total:** ~3 semanas (implementação incremental)

**Ordem de implementação:** US-01 → US-02 → US-04 → US-03 → US-05

## Onda 2+ (adiado)

- Notificações por e-mail (US-06) — in-app valida o loop no MVP
- Customização de template por empresa — sem evidência de necessidade antes de validar o padrão
- Histórico de relatórios com filtros — problema é de produção, não de consulta
- Integração com Slack/email como canal de coleta
- Analytics sobre conteúdo das narrativas

## Próximos passos

Após a Onda 1 em produção, medir por 60 dias:

1. Taxa de relatórios enviados no prazo: meta ≥70% (hoje: 52%)
2. NPS de líderes de time: meta ≥+15 (hoje: -8)
3. Churn mid-market: meta ≤4,5%/mês (hoje: 6,8%)

Se as métricas confirmarem a hipótese, avançar para Onda 2 com notificações
por e-mail e customização de template. Se não confirmarem, voltar ao Research
com os dados de uso da Onda 1 como nova fonte de evidência.
