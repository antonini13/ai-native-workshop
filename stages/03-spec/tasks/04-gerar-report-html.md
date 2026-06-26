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
- `output/03-spec-summary.md`

## Processador

Agente de IA

## Passos

1. **Extrair conteúdo-chave** de cada output:
   - Onboarding: empresa, problema, hipótese inicial
   - Research: declaração do problema, top 3 evidências, insight principal
   - Shape: visão em 1 frase, É/Não é, métricas de sucesso
   - Sketch: URL do Lovable ou descrição da interface
   - Spec: lista de tasks da Onda 1 com tamanhos

2. **Gerar o HTML** com esta estrutura de seções:
   - Header: nome do produto, data, subtítulo "Product Discovery Report"
   - Seção 1 — O Problema
   - Seção 2 — O que as Evidências Mostram (insights + dado mais forte)
   - Seção 3 — A Visão de Produto (visão + É/Não é)
   - Seção 4 — A Interface (sketch preview ou link)
   - Seção 5 — O Plano (tasks Onda 1 em cards)
   - Footer: gerado com AI-Native Workflow

3. **Estilo** — inline CSS ou Tailwind CDN. Aparência:
   - Fundo branco, fonte Inter (Google Fonts)
   - Largura máxima 860px, centrado, padding generoso
   - Headers em cinza-escuro (#111827), body em (#374151)
   - Seções separadas por linha fina (#E5E7EB)
   - Cards de task com borda esquerda azul (#2563EB)
   - Badges de tamanho (P/M/G) coloridos: verde/amarelo/laranja
   - Deve parecer um relatório profissional, não uma página web genérica

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
- [ ] Todas as 5 seções estão presentes com conteúdo real dos outputs
- [ ] Cards de task listam todas as stories da Onda 1
- [ ] Estilo é limpo e profissional — não parece gerado por IA
- [ ] Se há URL do Lovable sketch, está linkada na seção de interface

## Gate

Automático — este é o último passo do workflow.

Após escrever o arquivo, diga: "Report gerado em `output/report.html`. Abra
no browser para visualizar o discovery completo."
