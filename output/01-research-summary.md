# Research Summary — Kanvas

## Declaração do problema

O problema é que líderes de time no mid-market não preenchem os Relatórios
Automáticos do Kanvas com qualidade porque o formato atual os posiciona como
coletores de dados numéricos — não como narradores do que realmente aconteceu —
tornando o preenchimento um risco perceptivo (o relatório pode representar mal
o time) sem retorno visível (ninguém reage ao que foi escrito).

---

## Top 3 evidências

1. **NPS de líderes de time = -8, queda de -31% em uso vs -5,7% dos gestores** — fonte: analytics-report — por que sustenta: a insatisfação e o abandono estão concentrados exatamente no grupo que produz o relatório, não no que consome. O produto está perdendo sua fonte de insumo.

2. **`report_exported_csv` cresceu +214,7% de janeiro a junho** — fonte: analytics-report, corroborado por entrevistas 02, 04, 10 — por que sustenta: usuários não pararam de relatar — estão relatando fora do Kanvas. O crescimento das exportações é a evidência comportamental de que o problema é de formato, não de desinteresse em comunicar progresso.

3. **7 de 10 entrevistados descrevem o mesmo ponto de ruptura: o relatório não os representa** — fonte: entrevistas 02, 03, 06, 07, 08, 09, 10 — por que sustenta: a convergência qualitativa em fontes de perfis e empresas diferentes (gestor, líder técnico, CS, PM, CTO) indica um problema estrutural de design, não um problema de adoção individual.

---

## Insight principal

O onboarding apontava para hipóteses de UX ruim, falha de ativação ou pressão
competitiva. O Research revelou algo diferente: o produto tem um problema de
design de incentivos, não de interface.

A feature funciona exatamente em um caso — quando a mesma pessoa é ao mesmo
tempo quem sabe o contexto e quem preenche (caso Isabela, entrevista 05). Quando
os papéis se dividem — gestor consome, líder produz — o sistema cobra esforço de
quem não recebe o benefício. Sem incentivo, o produtor racionalmente abandona.

O que não era óbvio: o problema não é que o formulário é complicado. É que o
relatório, como desenhado, pode ativamente prejudicar o líder de time — mostrando
ao gestor uma semana de baixa velocidade sem o contexto de que havia um incidente
em produção, ou que o time priorizou dívida técnica. Preencher com cuidado vira
risco, não proteção.

---

## O que ainda não sabemos

- Se os gestores dão (ou tentam dar) feedback após ler os relatórios, ou se o produto não oferece mecanismo para isso. O loop quebrado pode ser comportamental ou de produto. — impacto na confiança: **alto**
- Taxa de abertura dos emails de relatório pelos gestores. Se gestores também não abrem, o abandono pode ter começado por eles, e a versão que chegou ao líder de time é "ninguém lê de qualquer jeito". — impacto na confiança: **alto**
- O que aconteceu entre janeiro e março para iniciar a curva de queda. Mudança no produto? Evento externo? — impacto na confiança: **médio**

---

## Pergunta de design para o Shape

Como poderíamos dar ao líder de time controle sobre a narrativa do seu trabalho
para que o relatório semanal represente o que realmente aconteceu — e criar um
loop de retorno visível que torne o preenchimento recompensador, não uma obrigação?
