# AI-Native Workshop — Product Discovery com IA

Demo de um fluxo completo de product discovery conduzido por IA: o agente passa
por quatro stages, do briefing inicial até tasks criadas no Linear.

O case é fictício, mas os problemas são reais.

---

## O que é isso

Um fluxo de product discovery onde um agente de IA conduz o processo passo a passo:

```
Onboarding → Research → Shape → Spec → Linear
```

Cada stage tem contratos de tarefa explícitos — arquivos que descrevem o objetivo,
os passos decompostos, o formato de output e os critérios de aceite. Você pode
ler qualquer arquivo em `stages/` e entender exatamente o que o agente vai fazer.

---

## Como usar

**Pré-requisitos:** Claude Code instalado (`npm install -g @anthropic-ai/claude-code`)

```bash
git clone https://github.com/[seu-usuario]/ai-native-workshop
cd ai-native-workshop
claude
```

Quando o Claude Code abrir, diga: `rodar o workflow` ou `começar o discovery`.

O agente vai conduzir o processo. Você interage nos gates de aprovação — momentos
em que o agente apresenta o resultado de um stage e aguarda sua confirmação antes
de continuar.

**Integrações opcionais:**
- Lovable MCP: para gerar o sketch de interface no Shape
- Linear MCP: para criar as tasks no Spec

Se não estiverem configurados, o agente usa fallbacks automáticos.

---

## O case: Kanvas

A Kanvas é um SaaS de gestão de projetos para times de médio porte. A feature
de Relatórios Automáticos — relatórios semanais de progresso enviados aos gestores
— está perdendo usuários. O churn no segmento mid-market está subindo.

O time de produto tem hipóteses. O discovery vai encontrar o que está acontecendo
de verdade.

---

## Estrutura do repositório

```
case/           → briefing do problema e respostas do onboarding
data/
  interviews/   → 10 entrevistas com usuários (qualitativo)
  metrics/      → relatório de analytics (quantitativo)
  competitive/  → análise de concorrentes
stages/
  00-onboarding/
  01-research/tasks/   → 3 contratos de task
  02-shape/tasks/      → 3 contratos de task
  03-spec/tasks/       → 3 contratos de task
output/         → arquivos gerados pelo agente durante o run
```

---

## Sobre os contratos de task

Cada arquivo em `stages/` é um **contrato de tarefa**: uma unidade de trabalho
com objetivo, processador, passos decompostos, formato de output e critérios de
aceite.

Esta é a estrutura que você pode usar para desenhar seus próprios workflows
de produto com IA. Decomponha uma tarefa que você já faz hoje — análise de
entrevistas, síntese de research, definição de escopo — e escreva um contrato
para ela.

---

## Criado por

Gabriel Antonini — consultoria em AI-Native para times e empresas de produto.

[linkedin.com/in/gabrielantonio] — substitua pelo link real antes de publicar.

---

*Este repositório é uma versão educacional simplificada, criada para o workshop
AI-Native Product Discovery. Para o sistema completo de workflows, entre em
contato.*
