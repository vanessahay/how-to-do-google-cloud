# 🤝 Guia de Contribuição e Boas Práticas

Para manter este repositório **público, seguro e reutilizável** para todos os clientes, siga as diretrizes abaixo ao adicionar ou atualizar manuais.

---

## 1. Sanitização e Anonimização de Dados (Obrigatório)

Antes de adicionar qualquer arquivo:
- **NUNCA inclua nomes reais de clientes**, marcas, unidades de negócio ou domínios corporativos privados.
- **NUNCA inclua identificadores reais de infraestrutura**, tais como:
  - `Project ID` ou `Project Number` reais;
  - `Organization ID` ou `Folder ID` reais;
  - Nomes de *Service Accounts*, endereços de e-mail, IPs ou *buckets* privados.
- Utilize sempre variáveis genéricas entre sinais de menor/maior:
  - `<ID_PROJETO_ORIGEM>`
  - `<ID_PROJETO_DESTINO>`
  - `<ID_PASTA_CORPORATIVA>`
  - `<DATASET_ORIGEM>` / `<DATASET_DESTINO>`

---

## 2. Prevenção de Vazamento de Credenciais (Pre-Commit Check)

Antes de executar `git commit` ou `git push`:
1. Inspecione os arquivos no *stage*:
   ```bash
   git status
   git diff --cached --name-only
   ```
2. Certifique-se de que nenhuma chave privada (`*.pem`, `id_rsa`), credencial de Service Account (`*.json`), token de API ou arquivo `.env` foi adicionado.

---

## 3. Padrão de Commits (Conventional Commits)

Utilizamos a especificação [Conventional Commits](https://www.conventionalcommits.org/pt-br/) para manter o histórico limpo e semântico:

- `docs(<escopo>): <descrição curta no imperativo>` — Adição ou atualização de manuais e templates.
- `feat(<escopo>): <descrição>` — Nova estrutura, script utilitário ou novo catálogo de playbooks.
- `fix(<escopo>): <descrição>` — Correção de comandos, queries SQL ou links quebrados.
- `chore: <descrição>` — Ajustes em `.gitignore`, configurações de repositório ou formatação.

**Exemplos:**
```bash
git commit -m "docs(bigquery): add project and Dataform corporate folder migration manual"
git commit -m "docs(templates): add reusable client communication template for BQ migration"
```
