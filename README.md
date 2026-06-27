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

## Como rodar (passo a passo)

### 1. Instalar o Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Precisa ter Node.js instalado. Para verificar: `node --version`

### 2. Autenticar

```bash
claude
```

Na primeira vez, abre o browser para autenticar com sua conta Anthropic.
Após autenticar, feche o Claude Code (`/exit`) e siga para o próximo passo.

### 3. Clonar o repositório

```bash
git clone https://github.com/antonini13/ai-native-workshop.git
cd ai-native-workshop
```

### 4. Abrir o Claude Code na pasta do workshop

```bash
claude
```

### 5. Iniciar o workflow

Dentro do Claude Code, escreva a mensagem:

```
iniciar
```

O agente vai exibir um banner de início e fazer a primeira pergunta do onboarding.

---

### Durante o onboarding

O agente faz **6 perguntas uma por vez**. Você responde como se fosse o Head of
Product da Kanvas. As respostas estão prontas para copiar e colar em
`case/onboarding-cheatsheet.md` — abra esse arquivo ao lado antes de começar.

### Gates de aprovação

Em 3 momentos o agente para e aguarda sua confirmação antes de continuar:
- Após o **Research** — "Esse diagnóstico faz sentido?"
- Após a **Visão de produto** — "Isso captura o que queremos construir?"
- Após o **Plano de build** — "A Onda 1 faz sentido como MVP?"

Responda com "sim" ou "pode continuar" para avançar.

---

**O que o agente gera:**
- Prompt de interface para colar em Lovable, v0 ou qualquer ferramenta de UI
- `output/tasks.json` com as tasks do MVP para importar na ferramenta de gestão do seu time

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

## Licença

[![CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

Este material está licenciado sob [Creative Commons Attribution-NonCommercial 4.0](LICENSE.md). Você pode compartilhar e adaptar livremente para fins não comerciais, desde que cite **Gabriel Antonini** como autor.

---

## Aviso importante

Este repositório é **material educacional**. O workflow aqui demonstrado é uma
versão simplificada criada para fins de aprendizado — não um sistema pronto para
uso em produção.

Implementar discovery com IA em ambientes reais de produto envolve muito mais:
contratos epistemológicos robustos, validação de evidências, gestão de viés nos
dados, integração com rituais existentes do time, calibração do modelo para o
contexto específico da empresa, e governança do processo. Nada disso está presente
aqui.

**Use este material para entender o conceito e experimentar. Não para substituir
um processo real de discovery.**

---

## Consultoria

Se você quer implementar workflows AI-Native no seu time de produto de verdade,
entre em contato.

**Gabriel Antonini**
Consultoria em AI-Native para times e empresas de produto.

[LinkedIn](https://www.linkedin.com/in/gab-antonini/)

---

> Este repositório é somente leitura. Sinta-se livre para clonar e explorar,
> mas contribuições externas não são aceitas.
