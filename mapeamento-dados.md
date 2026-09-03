# MAPEAMENTO DE DADOS — Auditoria Jacuzzi Brasil

## Estrutura de Pastas

```
NOVA ANALISE/
├── USADOS/                    ← 6 arquivos usados no dashboard
│   ├── Q1-Aquisicao-Trafego-PorCanal.csv
│   ├── Q2-Aquisicao-Trafego-PorCanal.csv
│   ├── Q1-Aquisicao-Usuarios-PorCanal.csv
│   ├── Q2-Aquisicao-Usuarios-PorCanal.csv
│   ├── Q1-Aquisicao-Leads-PorCanal.csv
│   └── Q1-PaginasDestino.csv
├── NAO-USADOS/                ← 16 arquivos exportados mas NÃO usados
│   ├── Q1-Aquisicao-Leads-PorOrigemMidia.csv
│   ├── Q1-Campanhas-NaoGoogle.csv
│   ├── Q1-Coortes-Aquisicao.csv
│   ├── Q1-Demograficos-Regiao.csv
│   ├── Q1-Engajamento-Retencap.csv
│   ├── Q1-Eventos.csv
│   ├── Q1-Paginas-Telas.csv
│   ├── Q1-PublicosAlvo.csv
│   ├── Q1-VisaoGeral-Aquisicao.csv
│   ├── Q1-VisaoGeral-GeracaoLeads.csv
│   ├── Q1-VisaoGeral-Retencap.csv
│   ├── Q1-VisaoGeral-Trafego.csv
│   ├── Q2-Engajamento.csv
│   ├── Q2-VisaoGeral-Aquisicao.csv
│   ├── Q2-VisaoGeral-GeracaoLeads.csv
│   └── Q3-VisaoGeral-GeracaoLeads.csv
└── GSC-CWV/                   ← 9 arquivos GSC/CrUX
    ├── GSC-AIFeatures.zip
    ├── GSC-Breadcrumbs.zip
    ├── GSC-Coverage.zip
    ├── GSC-CrawlStats.zip
    ├── GSC-CWV.zip
    ├── GSC-Https.zip
    ├── GSC-Links-Amostra.csv
    ├── GSC-Links-Recentes.csv
    └── GSC-PerformanceSearch.zip
```

---

## MAPEAMENTO: Dashboard → Fonte de Dado

### Slide "Aquisição completa" (Tráfego por canal)

| Métrica | Q1 | Fonte | Q2 | Fonte | Q3* | Fonte |
|---|---|---|---|---|---|---|
| **Sessões totais** | 43.612 | USADOS/Q1-Aquisicao-Trafego-PorCanal.csv | 38.457 | USADOS/Q2-Aquisicao-Trafego-PorCanal.csv | 22.650 | **⚠️ NÃO NOS CSVs** |
| Organic Search | 35.747 | idem | 30.212 | idem | 16.286 | **⚠️ NÃO NOS CSVs** |
| Direct | 6.430 | idem | 6.673 | idem | — | **⚠️ NÃO NOS CSVs** |
| Organic Social | 627 | idem | 622 | idem | — | **⚠️ NÃO NOS CSVs** |
| Paid Social | 0 | idem | 246 | idem | — | **⚠️ NÃO NOS CSVs** |
| AI Assistant | 0 | idem | 103 | idem | — | **⚠️ NÃO NOS CSVs** |
| Referral | 639 | idem | 413 | idem | — | **⚠️ NÃO NOS CSVs** |
| **71,9% busca** | — | — | — | — | 71,9% | **⚠️ NÃO NOS CSVs** |

### Slide "Aquisição completa" (Usuários)

| Métrica | Q1 | Fonte | Q2 | Fonte |
|---|---|---|---|---|
| **Usuários novos** | 25.843 | USADOS/Q1-Aquisicao-Usuarios-PorCanal.csv | 21.864 | USADOS/Q2-Aquisicao-Usuarios-PorCanal.csv |

### Slide "Funil completo" (Leads)

| Métrica | Q1 | Fonte | Q2 | Fonte | Q3* | Fonte |
|---|---|---|---|---|---|---|
| **Leads** | 5.862 | USADOS/Q1-Aquisicao-Leads-PorCanal.csv | 5.208 | **⚠️ NÃO NOS CSVs** | 2.802 | **⚠️ NÃO NOS CSVs** |

### Slide "Canais que fecham venda" (RD Station)

| Métrica | Valor | Fonte |
|---|---|---|
| **25 vendas** | R$ 812K total | **RD Station MCP API** (não CSV) |
| Google Ads (pago) | 7 vendas, R$ 220K | RD Station MCP API |
| Google (orgânico) | 3 vendas, R$ 129K | RD Station MCP API |
| Facebook/IG (orgânico) | 1 venda, R$ 48K | RD Station MCP API |
| Desconhecido | 12 vendas, R$ 331K | RD Station MCP API |

### Slide "Onde as pessoas entram" (Top páginas)

| Métrica | Fonte |
|---|---|
| Top páginas por sessões | USADOS/Q1-PaginasDestino.csv |

### Slide "Velocidade em verde" (CWV)

| Métrica | Fonte |
|---|---|
| Mobile Score 71→94 | CrUX API (live) |
| Desktop Score 82→96 | CrUX API (live) |
| LCP, INP, CLS | CrUX API (live) |

### Slide "Evolução de palavras-chave"

| Métrica | Fonte |
|---|---|
| Top 1-10: +15,9% (491→569) | GSC API (live) |
| 21-50: +24,6% (900→1.121) | GSC API (live) |
| Total: 3.175 (+11%) | GSC API (live) |
| AIO: 0→43 | GSC API (live) |

### Slide "Próxima fase"

| Métrica | Fonte |
|---|---|
| AI Assistant 0→103 sessões | USADOS/Q2-Aquisicao-Trafego-PorCanal.csv |

---

## ALERTAS CRÍTICOS

### 1. Q3* — Dados NÃO estão nos CSVs
Os números de sessões, tráfego por canal, leads e participação da busca para Q3 **não foram extraídos dos CSVs exportados**. Foram obtidos de fonte externa (possivelmente Power BI ou interface GA4). A pasta só contém dados semanais de geração de leads (05/07–15/08).

### 2. Q2 Leads — Dados NÃO estão nos CSVs
O número de 5.208 leads para Q2 **não tem fonte nos CSVs**. O arquivo `Q2-VisaoGeral-GeracaoLeads.csv` contém apenas dados Q1 (20260101–20260331) e Q3 (20260705–20260815) — **nenhum dado Q2**.

### 3. Q1 leads por canal (5.862) vs Q1 sessões (43.612)
- Sessões: 43.612 (arquivo: Q1-Aquisicao-Trafego-PorCanal.csv)
- Leads: 5.862 (arquivo: Q1-Aquisicao-Leads-PorCanal.csv)
- **Observação:** Sessões e Leads usam arquivos DIFERENTES. Sessões = "canal da sessão". Leads = "canal do primeiro usuário". Podem ter contagens diferentes.

### 4. Arquivos NÃO usados (16 arquivos exportados mas não consumidos)
Foram exportados do GA4 mas NÃO foram usados no dashboard:
- Q1-Aquisicao-Leads-PorOrigemMidia.csv
- Q1-Campanhas-NaoGoogle.csv
- Q1-Coortes-Aquisicao.csv
- Q1-Demograficos-Regiao.csv
- Q1-Engajamento-Retencap.csv
- Q1-Eventos.csv
- Q1-Paginas-Telas.csv
- Q1-PublicosAlvo.csv
- Q1-VisaoGeral-Aquisicao.csv
- Q1-VisaoGeral-GeracaoLeads.csv
- Q1-VisaoGeral-Retencap.csv
- Q1-VisaoGeral-Trafego.csv
- Q2-Engajamento.csv
- Q2-VisaoGeral-Aquisicao.csv
- Q2-VisaoGeral-GeracaoLeads.csv (CONTÉM SÓ Q1+Q3, NÃO Q2!)
- Q3-VisaoGeral-GeracaoLeads.csv

### 5. GSC/CWV — Arquivos ZIP não foram parseados
Os 9 arquivos GSC/CWV são ZIPs do Google Search Console. Foram usados como referência mas os números do dashboard vieram de APIs live (GSC API e CrUX API), não destes ZIPs.

---

## RESUMO PARA AUDITORIA COM POWER BI

| Dado no dashboard | Veio do CSV? | Veio do Power BI? | Veio de API? |
|---|---|---|---|
| Q1 sessões por canal | ✅ SIM | — | — |
| Q2 sessões por canal | ✅ SIM | — | — |
| Q3 sessões por canal | — | ❓ VERIFICAR | — |
| Q1 usuários novos | ✅ SIM | — | — |
| Q2 usuários novos | ✅ SIM | — | — |
| Q1 leads por canal | ✅ SIM | — | — |
| Q2 leads | — | ❓ VERIFICAR | — |
| Q3 leads | — | ❓ VERIFICAR | — |
| 71,9% participação busca Q3 | — | ❓ VERIFICAR | — |
| Vendas RD Station | — | — | ✅ MCP API |
| CWV (LCP, INP, CLS) | — | — | ✅ CrUX API |
| Palavras-chave GSC | — | — | ✅ GSC API |
| AI Assistant | ✅ SIM (Q2) | — | — |
| Top páginas | ✅ SIM (Q1) | — | — |
