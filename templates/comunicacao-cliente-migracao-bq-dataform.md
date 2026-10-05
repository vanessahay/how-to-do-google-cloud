# ✉️ Template de Comunicação: Migração de Projeto BigQuery & Dataform para Pasta Corporativa

> **Como usar:** Copie o bloco abaixo e substitua os campos `<NOME_DO_PROJETO>` antes de enviar ao cliente por e-mail ou chat.

---

**Assunto:** Migração do projeto `<NOME_DO_PROJETO>` (BigQuery e Dataform) para a Nova Pasta Corporativa

Olá, pessoal! Tudo bem?

Analisamos a dúvida sobre a transição do ambiente **`<NOME_DO_PROJETO>`** para a nova pasta corporativa e trazemos uma excelente notícia: **não será necessário recriar nada do zero e não haverá perda de nenhum dado histórico acumulado.**

O Google Cloud oferece dois caminhos oficiais e seguros para essa transição, dependendo da diretriz de governança definida para a nova pasta:

### Opção 1 — Mover o Projeto existente diretamente para a Nova Pasta Corporativa (Mais simples e rápido)
No Google Cloud, tabelas do BigQuery e pipelines do Dataform ficam vinculados ao Projeto. É possível mover o projeto `<NOME_DO_PROJETO>` inteiro diretamente para dentro da nova pasta corporativa via *Resource Manager*.
* **Impacto:** Zero tempo de inatividade (operação apenas de metadados). Todas as tabelas, dados acumulados, *views* e ETLs do Dataform permanecem 100% intactos no mesmo lugar. Apenas as políticas de permissão (IAM) e regras da nova pasta passam a ser herdadas.
* **Documentação Oficial:**
  * [Hierarquia de Recursos no BigQuery](https://docs.cloud.google.com/bigquery/docs/resource-hierarchy)
  * [Movimentação de Projetos entre Pastas](https://docs.cloud.google.com/resource-manager/docs/moving-projects-folders)

### Opção 2 — Caso a governança exija um NOVO Projeto (`Project ID` novo) dentro da Pasta Corporativa
Mesmo que seja obrigatório transferir a estrutura para um novo projeto recém-criado na pasta corporativa, tudo é reaproveitado em dois passos:
1. **Cópia nativa dos Dados Acumulados (BigQuery):** Utilizamos o recurso oficial de [Cópia de Datasets](https://docs.cloud.google.com/bigquery/docs/copying-datasets) e [Cópia de Tabelas](https://docs.cloud.google.com/bigquery/docs/managing-tables#copy-table) para transferir todas as tabelas e partições históricas entre os projetos de forma nativa, sem precisar reprocessar dados passados.
2. **Migração dos ETLs do Dataform:** Como os pipelines do Dataform são baseados em código versionado no Git, basta conectar o repositório do Dataform no novo projeto ao mesmo repositório Git ([Conectar repositório Dataform](https://docs.cloud.google.com/dataform/docs/connect-repository)), alterar a variável `defaultProject` para o ID do projeto novo ([Release Configurations](https://docs.cloud.google.com/dataform/docs/release-configurations)) e rodar as execuções normais (**sem** *Full Refresh*). O Dataform recriará todas as *views* automaticamente e continuará alimentando as tabelas incrementais a partir do histórico já copiado ([Tabelas Incrementais no Dataform](https://docs.cloud.google.com/dataform/docs/incremental-tables)).

Para o passo a passo técnico completo (com comandos `gcloud`, `bq`, SQL e checklist de validação), consulte nosso [Manual de Migração BigQuery & Dataform](../manuais/bigquery-dataform/migracao-projeto-e-pasta-corporativa.md).

Ficamos à disposição para apoiar o time de Cloud/Governança na escolha e execução da abordagem!
