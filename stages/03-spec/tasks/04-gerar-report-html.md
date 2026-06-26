---
task_id: spec/gerar-report-html
processador: agente
gate: automatico
---

# Gerar Report Visual (HTML)

## Objetivo

Transformar todos os outputs do workflow num único arquivo HTML que pode ser
aberto no browser e apresentado numa tela. É o artefato final do discovery —
do problema ao plano, numa página só.

## Contexto

Leia todos os outputs gerados:
- `output/00-onboarding-summary.md`
- `output/01-research-summary.md`
- `output/shape-02-vision.md`
- `output/shape-03-sketch.md`
- `output/spec-prd.md`
- `output/03-spec-summary.md`

## Processador

Agente de IA

## Passos

1. **Extrair conteúdo-chave** de cada output:
   - Onboarding: empresa, problema, restrição principal
   - Research: declaração do problema, top 3 evidências, insight principal, pergunta de design
   - Shape: visão em 1 frase, tabelas É/Não é e Faz/Não faz, métricas de sucesso
   - Sketch: URL do Lovable (para iframe) ou descrição da interface
   - Spec: PRD completo + lista de tasks da Onda 1 com tamanhos e links do Linear

2. **Gerar o HTML** com esta estrutura de seções:
   - **Header:** nome do produto, data, badge "Product Discovery Report", linha com empresa e contexto
   - **Seção 1 — O Problema:** declaração em destaque + 3 bullets de evidência com dado/fonte
   - **Seção 2 — O Insight:** o "aha" do Research em destaque (bloco com fundo levemente colorido) + pergunta de design
   - **Seção 3 — A Visão de Produto:** visão em 1 frase grande + tabelas É/Não é e Faz/Não faz lado a lado + métricas de sucesso em 3 cards
   - **Seção 4 — A Interface:** iframe com preview do Lovable (width 100%, height 500px) ou bloco descritivo se não houver URL; link externo para abrir em tela cheia
   - **Seção 5 — O Plano:** cards das tasks da Onda 1 com borda esquerda azul, badge de tamanho colorido e link para a issue no Linear; abaixo: lista resumida da Onda 2+
   - **Footer:** "Gerado em [data] com AI-Native Workflow · do briefing ao Linear em [N] minutos"

3. **Estilo** — Tailwind CDN + Inter. Aparência:
   - Fundo #F9FAFB, fonte Inter (Google Fonts)
   - Largura máxima 900px, centrado, padding generoso
   - Cada seção tem um número (01, 02...) em azul claro antes do título
   - Headers em (#111827), body em (#374151)
   - Seções em cards brancos com borda (#E5E7EB) e border-radius
   - Cards de task com borda esquerda azul (#2563EB) e link clicável para o Linear
   - Badges de tamanho: P = verde (#059669), M = amarelo (#D97706), G = laranja (#EA580C)
   - Métricas de sucesso em 3 cards lado a lado com número grande em azul
   - Deve parecer um deliverable profissional de consultoria, não uma página web genérica

## Formato de output

**Escreva:** `output/report.html`

Arquivo HTML completo e auto-suficiente — deve abrir corretamente no browser
com duplo clique, sem servidor, sem dependências locais.

Use Tailwind via CDN para estilização:
```html
<link href="https://cdn.tailwindcss.com" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

## Critérios de aceite

- [ ] Arquivo abre no browser sem erros
- [ ] Todas as 6 seções estão presentes com conteúdo real dos outputs
- [ ] Seção de interface tem iframe do Lovable (ou bloco descritivo com link)
- [ ] Cards de task da Onda 1 têm link clicável para a issue no Linear
- [ ] Métricas de sucesso aparecem em 3 cards lado a lado
- [ ] Badges de tamanho (P/M/G) estão coloridos corretamente
- [ ] Footer menciona o workflow e a data de geração
- [ ] Estilo é limpo e profissional — parece um deliverable real, não uma página genérica

## Gate

Automático — este é o último passo do workflow.

Após escrever o arquivo, diga: "Report gerado em `output/report.html`. Abra
no browser para visualizar o discovery completo."
