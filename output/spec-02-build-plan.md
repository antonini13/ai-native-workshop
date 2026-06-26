# Plano de Build — Relatório Contextual Kanvas

## Onda 1 — MVP

| Story | Título | Tamanho | Depende de | Por que é MVP |
|-------|--------|---------|------------|---------------|
| US-01 | Campo de narrativa como elemento central | M | — | É a inversão de hierarquia que resolve o problema core — sem isso, nada muda para o líder |
| US-02 | Dados automáticos como complemento visual | P | US-01 | A inversão só é completa se os dados forem subordinados; sem isso US-01 ainda compete com os números |
| US-03 | Envio e indicador de status de leitura | M | US-01, US-02 | Sem o indicador de leitura, o líder não sabe se valeu a pena preencher — o loop começa aqui |
| US-04 | Leitura pelo gestor com narrativa em destaque | M | US-01 | Sem a tela do gestor, a narrativa nunca chega a quem deveria ler |
| US-05 | Reação e comentário do gestor | M | US-04 | Fecha o loop de feedback — sem reação visível, o ciclo de abandono não muda |

**Estimativa total Onda 1:** ~3 semanas (time pequeno, implementação incremental)

---

## Checagem de coerência

O conjunto da Onda 1 resolve o seguinte problema identificado no Research:

> Líderes de time não preenchem os relatórios com qualidade porque o formato atual os trata como coletores de dados, tornando o preenchimento um risco perceptivo (pode representar mal o time) sem retorno visível (ninguém reage ao que foi escrito).

**Resolve? Sim.**

- US-01 + US-02 eliminam o risco perceptivo: a narrativa do líder controla a história, os dados entram como suporte.
- US-03 + US-05 criam o retorno visível: o líder sabe que foi lido e recebe uma resposta.
- US-04 garante que o gestor recebe o que o líder escreveu com a hierarquia correta.

O único elemento do Research não coberto no MVP é a notificação por e-mail (US-06) — mas a notificação in-app de US-05 é suficiente para testar se o loop de feedback muda o comportamento de preenchimento.

---

## Onda 2+

| Story | Título | Motivo do adiamento |
|-------|--------|---------------------|
| US-06 | Notificações por e-mail | Notificação in-app (US-05) valida o loop no MVP; e-mail adiciona alcance mas não muda a hipótese a ser testada |
| — | Customização de template por empresa | Complexidade de configuração e suporte sem evidência de que o template padrão de 3 seções não serve para a maioria |
| — | Histórico de relatórios com filtros | Útil para gestores com múltiplos times, mas não é o momento crítico identificado no Research (o problema é de produção, não de consulta) |
| — | Integração com Slack/email como canal de coleta | Workaround que usuários já fazem manualmente; pode ser endereçado depois de o loop funcionar dentro do Kanvas |
| — | Analytics sobre conteúdo das narrativas | Feature de valor para o negócio, não para o usuário — prematura antes de o uso de narrativa estar estabelecido |

---

## Notas de incerteza

- **US-01 (M):** Estimativa assume que a tela de preenchimento atual é refatorável sem reescrita do backend. Se o relatório atual tiver acoplamento forte entre campos e schema de dados, pode escalar para G. Investigar antes de iniciar.
- **US-03 (M):** O indicador de status de leitura requer rastrear `viewed_at` por usuário por relatório. Se esse evento ainda não existe no pipeline de analytics, adiciona 1–2 dias de instrumentação.
- **US-05 (M):** Reações e comentários exigem modelo de dados novo (comentário vinculado ao relatório, reação como enum). Dependência de US-04 em produção antes de ser testável end-to-end.
