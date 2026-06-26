---
task_id: shape/sketch-lovable
processador: agente + ferramenta-externa (Lovable via MCP)
gate: humano
---

# Sketch de Interface

## Objetivo

Criar uma representação visual da solução para tornar a visão concreta. O sketch
não é um protótipo final — é uma ferramenta de alinhamento que transforma palavras
em algo que se pode ver, tocar e reagir.

Um sketch bem feito revela ambiguidades que o texto não revelou. Se alguém olhar
e disser "não era isso que eu imaginei", o sketch fez seu trabalho.

Nota: em projetos reais, o design system da empresa seria usado aqui. Neste demo,
usamos shadcn/ui como padrão. O resultado serve como referência de estrutura e
fluxo, não de identidade visual final.

## Contexto

Leia `output/shape-02-vision.md`. Use a visão aprovada como base para o sketch.

## Processador

Agente de IA + Ferramenta externa: Lovable (via MCP `mcp__lovable__create_project`)

Fallback automático se Lovable indisponível: gerar prompt estruturado para uso
manual em qualquer ferramenta de geração de UI.

## Passos

1. **Definir a tela principal** — Identifique a tela que representa o core da
   solução. Qual é a interface que o usuário mais afetado vai usar no momento
   crítico identificado no Research? Justifique a escolha.

2. **Listar componentes** — Quais elementos precisam aparecer nessa tela?
   (campos de texto, botões, visualizações de dados, estados de interface,
   navegação, indicadores de status)

3. **Tentar Lovable MCP** — Chame `mcp__lovable__create_project` com
   `workspace_id` disponível e uma `initial_message` detalhada contendo:
   - Contexto do produto: quem usa, para quê, qual problema resolve
   - Tela principal: nome, propósito, o que o usuário faz nela
   - Componentes esperados com descrição de cada um
   - Estilo: clean, profissional, B2B, shadcn/ui
   - Instrução explícita: "não use dados reais de usuários, use dados fictícios
     de exemplo"

4. **Se Lovable disponível** — Após criar o projeto, registre a preview URL
   e a editor URL. Descreva brevemente o que foi construído.

5. **Se Lovable indisponível (fallback)** — Gere um prompt completo e
   auto-suficiente para uso manual. Quem copiar e colar esse prompt em Lovable
   (lovable.dev), v0 (v0.dev), ou ferramenta similar não deve precisar de
   nenhum contexto adicional.

Após gerar o sketch ou o prompt de fallback, escreva também
`output/02-shape-summary.md` consolidando os outputs do Shape: oportunidade,
visão e sketch.

## Formato de output

**Escreva:** `output/shape-03-sketch.md`

Quando Lovable disponível:
```
## Sketch gerado com Lovable

Preview: [URL]
Editor: [URL]

### O que foi construído
[Descrição da tela principal e dos componentes]

### Tela: [nome]
[O que o usuário faz nessa tela e como os componentes se relacionam]
```

Quando usar fallback:
```
## Prompt para geração manual de interface

Cole este prompt no Lovable (lovable.dev), v0 (v0.dev), ou ferramenta similar:

---
[Prompt completo e auto-suficiente — contexto, tela, componentes, estilo]
---

### Tela principal: [nome]
[Descrição detalhada dos elementos visuais e do fluxo]

### Componentes principais
| Componente | Propósito |
|------------|-----------|
```

**Escreva também:** `output/02-shape-summary.md`

```
## Shape Summary

### Oportunidade
[1 parágrafo da declaração de oportunidade]

### Visão
[Visão em 1 frase + tabelas É/Não é e Faz/Não faz]

### Sketch
[URL do Lovable ou indicação de que o prompt de fallback está em shape-03-sketch.md]

### Métricas de sucesso
[Lista das 3 métricas]
```

## Critérios de aceite

- [ ] Tela principal está definida e justificada pela visão aprovada
- [ ] Lovable foi chamado OU prompt de fallback está completo e auto-suficiente
- [ ] `output/02-shape-summary.md` foi escrito
- [ ] Prompt de fallback (se usado) funciona sem contexto adicional

## Gate

Humano — apresente o resultado ao usuário e aguarde aprovação explícita antes
de continuar para o Spec.

Se Lovable funcionou: "Aqui está o sketch. Isso captura a direção visual?
Podemos ir para o Spec?"

Se fallback: "O Lovable não estava disponível. Aqui está o prompt para você
gerar o sketch manualmente. Quando quiser continuar, diga 'pode ir pro Spec'."

Não continue até receber confirmação.
