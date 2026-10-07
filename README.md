# ☁️ How-To Google Cloud — Guias Práticos de Arquitetura e Dados

Repositório de guias técnicos passo a passo, boas práticas e referências de arquitetura no **Google Cloud**, baseados na documentação oficial.

---

## 📚 Manuais Disponíveis

### BigQuery & Dataform
* **[Migração de Projetos, Tabelas e ETLs para Nova Pasta Corporativa](./manuais/bigquery-dataform/migracao-projeto-e-pasta-corporativa.md)**
  Guia completo passo a passo sobre como reorganizar projetos existentes no Google Cloud ou migrar datasets históricos do BigQuery e pipelines do Dataform para uma nova pasta corporativa **sem necessidade de recriar recursos do zero** e **sem perda de dados acumulados**.
  * **Cenário 1:** Movimentação do projeto existente para a nova pasta corporativa via *Resource Manager* (zero *downtime* e sem movimentação física de dados).
  * **Cenário 2:** Cópia nativa de datasets/tabelas do BigQuery (*Dataset Copy*, *Table Copy* e *Table Clones*) e migração de repositórios Git do Dataform para um novo `Project ID` preservando o histórico incremental.

### Google Analytics 4 (GA4) & BigQuery
* **[Ingestão Streaming do GA4 (Free) no BigQuery: Configuração e Melhores Práticas](./manuais/google-analytics-4/ingestao-streaming-ga4-bigquery.md)**
  Guia completo para configurar a exportação contínua (**Streaming Export**) de propriedades gratuitas do GA4 para o BigQuery, incluindo pré-requisitos de faturamento e IAM, diferenças entre as tabelas `events_intraday_YYYYMMDD` e `events_YYYYMMDD`, limites de volume, consultas SQL otimizadas com `_TABLE_SUFFIX` e modelo incremental pronto para **Dataform**.

---

## 🔗 Documentação Oficial de Referência

* [Documentação do BigQuery](https://docs.cloud.google.com/bigquery/docs)
* [Documentação do Dataform](https://docs.cloud.google.com/dataform/docs)
* [Documentação do Resource Manager](https://docs.cloud.google.com/resource-manager/docs)
* [Documentação do BigQuery Export no Google Analytics 4](https://support.google.com/analytics/answer/9358801?hl=pt-BR)
