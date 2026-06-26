# Spec Summary — Kanvas Weekly

## O problema resolvido

Líderes de time não conseguem comunicar o contexto real do seu trabalho semanal porque o Kanvas posiciona dados automáticos como conteúdo principal do relatório e narrativa do time como detalhe secundário — fazendo o relatório representar mal o trabalho e quebrando o ciclo de visibilidade que o produto prometia.

## A aposta

Para líderes de time que precisam reportar progresso para gestores que não acompanham o trabalho diário, o Kanvas Weekly é uma atualização semanal estruturada que coloca a narrativa do time em primeiro lugar — com os dados automáticos do projeto como contexto, não como protagonistas.

## Tasks criadas — Onda 1

| Story | Título | Tamanho | Depende de |
|-------|--------|---------|------------|
| US-01 | Preencher narrativa como destaque do relatório | M (3–5 dias) | — |
| US-03 | Salvar rascunho automaticamente | P (1–2 dias) | US-01 |
| US-02 | Enviar relatório com narrativa + dados | M (3–5 dias) | US-01 |
| US-04 | Gestor recebe relatório com narrativa em destaque | M (3–5 dias) | US-02 |

**Estimativa total:** 10–17 dias úteis (~2–3 semanas, 1 dev full-stack)

*Tasks exportadas em `output/linear-tasks.json` — importar no Linear quando a autenticação estiver ativa.*

## Onda 2+ (adiado)

- US-05: Histórico de relatórios anteriores — útil mas não bloqueia validação
- Loop de feedback do gestor para o líder — causa secundária; entra após o preenchimento voltar
- Lembretes automáticos — o problema não é esquecimento, é formato; entra depois
- Campos customizáveis por time — decisão de produto deliberada para v1

## Próximos passos

1. Importar `output/linear-tasks.json` no Linear (via Forge com autenticação ativa)
2. Gerar sketch no Lovable usando o prompt em `output/shape-03-sketch.md`
3. Planning da Onda 1: checar schema de `report_configured` antes de estimar US-01 (pode ser G se estrutura for rígida)
4. Checar como o email de relatório atual é gerado antes de estimar US-04 (pode ser G se for template hardcoded)
5. Após MVP: medir `report_configured`, taxa de envio no prazo e churn mid-market em 60 e 90 dias
