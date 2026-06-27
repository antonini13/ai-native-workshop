---
task_id: shape/sketch
processador: agente
gate: humano
---

# Sketch de Interface

## Objetivo

Criar um prompt completo e auto-suficiente para geração da interface principal
da solução. O prompt pode ser colado em qualquer ferramenta de geração de UI
(Lovable, v0, Figma AI, etc.) sem precisar de contexto adicional.

O sketch não é um protótipo final — é uma ferramenta de alinhamento que
transforma palavras em algo que se pode ver, tocar e reagir. Um bom prompt
revela ambiguidades que o texto não revelou.

## Contexto

Leia `output/shape-02-vision.md`. Use a visão aprovada como base.

## Processador

Agente de IA

## Passos

1. **Definir a tela principal** — Identifique a tela que representa o core da
   solução. Qual é a interface que o usuário mais afetado vai usar no momento
   crítico identificado no Research? Justifique a escolha em 1-2 linhas.

2. **Listar componentes** — Quais elementos precisam aparecer nessa tela?
   (campos de texto, botões, visualizações de dados, estados de interface,
   navegação, indicadores de status)

3. **Escrever o prompt** — Gere um prompt completo e auto-suficiente contendo:
   - Contexto do produto: quem usa, para quê, qual problema resolve
   - Tela principal: nome, propósito, o que o usuário faz nela
   - Componentes esperados com descrição visual de cada um
   - Dados fictícios de exemplo preenchidos (não use dados reais)
   - Direção visual: "Use Tailwind CSS e shadcn/ui. Estilo inspirado no
     design do Linear — fundo branco (#FFFFFF), tipografia Inter, sidebar
     esquerda em cinza-escuro (#111827), cards com borda fina (#E5E7EB),
     sem sombras pesadas, sem gradientes. Cor de ação principal: azul
     (#2563EB). Produto B2B real, não template genérico."
   - O que NÃO fazer (evitar elementos que contradizem a solução)

Após concluir, escreva também `output/02-shape-summary.md` consolidando
os outputs do Shape: oportunidade, visão e sketch.

## Formato de output

**Escreva:** `output/shape-03-sketch.md`

```
## Tela principal: [nome]

**Justificativa:** [por que esta tela representa o core da solução]

---

## Prompt para geração de interface

Cole este prompt no Lovable (lovable.dev), v0 (v0.dev), ou ferramenta similar:

---

[Prompt completo e auto-suficiente]

---

### Componentes principais

| Componente | Propósito |
|------------|-----------|
```

**Escreva também:** `output/02-shape-summary.md`

```
## Oportunidade
[1 parágrafo da declaração de oportunidade]

## Visão
[Visão em 1 frase + tabelas É/Não é e Faz/Não faz]

## Sketch
[Indicação de que o prompt está em output/shape-03-sketch.md]

## Métricas de sucesso
[Lista das 3 métricas]
```

## Critérios de aceite

- [ ] Tela principal está definida e justificada pela visão aprovada
- [ ] Prompt é auto-suficiente — quem colar em qualquer ferramenta não precisa de contexto adicional
- [ ] Prompt inclui dados fictícios de exemplo preenchidos
- [ ] `output/02-shape-summary.md` foi escrito

## Gate

Humano — apresente o prompt ao usuário e aguarde aprovação antes de ir para o Spec.

Diga: "Aqui está o prompt de sketch. Cole em Lovable, v0 ou qualquer ferramenta
de UI de sua preferência. Quando estiver satisfeito com a direção visual, diga
'pode ir pro Spec'."

Não continue até receber confirmação.
