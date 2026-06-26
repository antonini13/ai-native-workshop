# Relatório de Analytics — Kanvas
**Período:** Janeiro a Junho 2026 (últimos 6 meses)
**Exportado em:** 20/06/2026

---

## Visão geral do produto

| Métrica | Jan | Fev | Mar | Abr | Mai | Jun |
|---------|-----|-----|-----|-----|-----|-----|
| MAU total | 14.200 | 14.650 | 14.890 | 14.320 | 13.780 | 13.240 |
| Sessões/dia (média) | 4.100 | 4.380 | 4.290 | 4.010 | 3.820 | 3.650 |
| Retenção D30 | 71% | 72% | 71% | 68% | 65% | 63% |

---

## Feature: Relatórios Automáticos

### Usuários ativos mensais por tipo de perfil

| Perfil | Jan | Fev | Mar | Abr | Mai | Jun | Variação |
|--------|-----|-----|-----|-----|-----|-----|---------|
| Gestores (visualizadores) | 1.940 | 1.980 | 2.010 | 1.890 | 1.850 | 1.830 | **-5,7%** |
| Líderes de time (configuradores) | 2.840 | 2.790 | 2.680 | 2.410 | 2.180 | 1.960 | **-31,0%** |

> Nota: "Gestores" são usuários com permissão de leitura que visualizam os relatórios.
> "Líderes de time" são usuários que preenchem e enviam os relatórios.

### Eventos-chave por mês

| Evento | Jan | Fev | Mar | Abr | Mai | Jun | Variação |
|--------|-----|-----|-----|-----|-----|-----|---------|
| `report_configured` (relatório preenchido) | 8.420 | 8.180 | 7.640 | 6.890 | 5.980 | 5.230 | **-37,9%** |
| `report_viewed` (relatório aberto por gestor) | 6.910 | 6.840 | 6.720 | 6.480 | 6.310 | 6.180 | **-10,6%** |
| `report_exported_csv` (exportação para planilha) | 340 | 390 | 580 | 890 | 1.240 | 1.070 | **+214,7%** |
| `report_skipped` (relatório da semana não enviado) | 1.820 | 1.970 | 2.340 | 2.980 | 3.510 | 3.890 | **+113,7%** |

### Tempo médio para completar um relatório

| Período | Tempo médio |
|---------|------------|
| Jan–Fev | 8 min |
| Mar–Abr | 14 min |
| Mai–Jun | 22 min |

> Possível explicação: usuários menos habituados estão tentando preencher mais
> campos opcionais sem saber exatamente o que colocar.

### Taxa de envio no prazo

| Período | Relatórios enviados no prazo |
|---------|------------------------------|
| Jan–Fev | 87% |
| Mar–Abr | 71% |
| Mai–Jun | 52% |

---

## Segmentação por tamanho de empresa

### Variação no uso de Relatórios Automáticos (Jan vs Jun, configuradores)

| Segmento | Variação |
|----------|---------|
| Pequeno (< 50 funcionários) | -11% |
| Médio-baixo (50–150 funcionários) | **-44%** |
| Médio-alto (150–300 funcionários) | **-38%** |
| Grande (300–500 funcionários) | -19% |
| Enterprise (500+) | -12% |

> A queda está concentrada no segmento mid-market (50–300 funcionários).

---

## Correlação com churn

### Churn mensal por segmento

| Segmento | Jan | Mar | Jun |
|----------|-----|-----|-----|
| Mid-market (50–300 func.) | 3,2% | 4,8% | 6,8% |
| Demais segmentos (média) | 2,1% | 2,3% | 2,4% |

### Análise de comportamento pré-churn

Accounts que cancelaram nos últimos 60 dias vs accounts ativas no mesmo período:

| Comportamento | Accounts churned | Accounts ativas |
|---------------|-----------------|----------------|
| Taxa de relatórios enviados no prazo | 28% | 71% |
| Eventos `report_exported_csv` por mês | 4,2 | 0,8 |
| Eventos `report_configured` por mês | 2,1 | 7,4 |

**Correlação identificada:** accounts com menos de 30% de relatórios enviados no
prazo têm **4,2x mais probabilidade** de churn nos próximos 90 dias.

---

## Outros dados relevantes

### Canais de suporte relacionados a Relatórios Automáticos

| Período | Tickets abertos sobre a feature |
|---------|---------------------------------|
| Jan–Fev | 82 tickets |
| Mar–Abr | 164 tickets |
| Mai–Jun | 231 tickets |

Categorias mais frequentes nos tickets (Mai–Jun):
1. "Como preencher o relatório" — 38%
2. "Relatório não apareceu para o gestor" — 27%
3. "Quero adicionar mais informações mas não tem campo" — 21%
4. "Como desativar o envio automático" — 14%

### NPS segmentado por perfil (último trimestre)

| Perfil | NPS |
|--------|-----|
| Gestores | +34 |
| Líderes de time | **-8** |

> Gestores estão relativamente satisfeitos com o produto em geral.
> Líderes de time têm NPS negativo — dado incomum para este segmento.
