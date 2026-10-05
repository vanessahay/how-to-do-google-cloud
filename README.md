# ☁️ Google Cloud — Manuais e Playbooks de Arquitetura & Dados

Bem-vindo ao repositório público de **Manuais Técnicos, Guias Passo a Passo e Playbooks de Migração no Google Cloud**.

Este repositório foi estruturado para fornecer guias práticos, referências arquiteturais e procedimentos operacionais baseados na **documentação oficial do Google Cloud**, prontos para serem compartilhados com clientes, arquitetos e engenheiros de dados.

---

## 📚 Catálogo de Manuais

| Categoria | Manual | Descrição |
| :--- | :--- | :--- |
| **BigQuery & Dataform** | [Migração de Projetos, Tabelas e ETLs para Nova Pasta Corporativa](./manuais/bigquery-dataform/migracao-projeto-e-pasta-corporativa.md) | Guia passo a passo para mover projetos existentes ou migrar datasets históricos do BigQuery e pipelines do Dataform para uma nova hierarquia corporativa **sem perda de dados acumulados** e **sem retrabalho**. |

---

## 📝 Templates de Comunicação

| Template | Descrição |
| :--- | :--- |
| [Template de E-mail/Mensagem: Migração BigQuery & Dataform](./templates/comunicacao-cliente-migracao-bq-dataform.md) | Modelo executivo pronto para preenchimento e envio a clientes com dúvidas sobre preservação de histórico na reorganização de projetos GCP. |

---

## 🗂️ Estrutura do Repositório

```text
.
├── README.md                                                 # Índice geral e visão do repositório
├── CONTRIBUTING.md                                           # Boas práticas de contribuição e segurança
├── .gitignore                                                # Proteção contra commit de credenciais e arquivos locais
├── manuais/
│   └── bigquery-dataform/
│       └── migracao-projeto-e-pasta-corporativa.md           # Guia técnico completo passo a passo
└── templates/
    └── comunicacao-cliente-migracao-bq-dataform.md           # Template reutilizável para resposta a clientes
```

---

## 🔒 Segurança e Privacidade (Repositório Público)

Este é um repositório **público e compartilhável**. Todos os guias seguem rigorosamente as seguintes diretrizes:
1. **Zero Dados Confidenciais de Clientes (Data Sanitization):** Nomes de clientes, identificadores reais de projetos (`Project ID`), números de organização (`Organization ID`) ou nomes de tabelas internas nunca são versionados. Utilize sempre placeholders padronizados (ex.: `<ID_PROJETO_ORIGEM>`, `<ID_PROJETO_DESTINO>`, `<ID_PASTA_CORPORATIVA>`).
2. **Zero Credenciais ou Chaves:** Chaves de contas de serviço (`*.json`), arquivos `.env`, certificados (`*.pem`) e tokens são bloqueados via `.gitignore` e validados por scanner de segredos no pré-commit.
3. **Referências Oficiais:** Todos os procedimentos apontam diretamente para a documentação oficial (`https://docs.cloud.google.com`).

---

## 📄 Licença

Distribuído sob a licença **Apache 2.0**. Consulte a documentação oficial do Google Cloud para termos de serviço específicos de cada produto.
