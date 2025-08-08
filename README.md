# Guia: Criando Banco de Dados no Azure (Azure SQL Database)

Este guia mostra o passo a passo para criar um **Azure SQL Database** no Portal Azure, além de explicar cada uma das principais opções de configuração.

---

## Pré-requisitos

- Conta Microsoft com acesso ao portal Azure.
- Uma assinatura ativa no Azure.
- Permissão para criar recursos (ou seja, Contributor ou superior).

---

## Passo a Passo para Criar um Banco de Dados SQL

### 1. Acesse o Portal Azure

- Navegue até: [https://portal.azure.com](https://portal.azure.com)

---

### 2. Acesse "SQL databases"

- No menu lateral, clique em **"SQL databases"**.
- Ou utilize a barra de pesquisa superior digitando: `SQL databases`.
- Clique em **+ Create** ou **+ Add**.

---

### 3. Guia "Basics" (Informações Básicas)

| Campo                  | Descrição |
|------------------------|-----------|
| **Subscription**       | Selecione sua assinatura do Azure. |
| **Resource Group**     | Selecione um grupo de recursos existente ou crie um novo. |
| **Database Name**      | Nome do banco de dados. |
| **Server**             | Selecione um servidor SQL existente ou crie um novo. |
| **Want to use Elastic Pool?** | Escolha se o banco fará parte de um pool elástico. |
| **Compute + Storage**  | Defina o modelo de compra (vCore ou DTU), tamanho e desempenho. |

---

### 🖥️ Criando um Novo Servidor SQL

Se você optar por criar um novo servidor, informe:

| Campo                | Descrição |
|----------------------|-----------|
| **Server name**      | Nome único global. |
| **Server admin login** | Nome do usuário administrador. |
| **Password**         | Senha forte para acesso. |
| **Location**         | Região onde o servidor será hospedado. |

---

### 4. Guia "Networking"

| Campo                    | Descrição |
|--------------------------|-----------|
| **Connectivity Method**  | Método de conexão (geralmente "Public endpoint"). |
| **Firewall rules**       | Defina regras para permitir IPs específicos acessarem o banco. |
| **Connection Policy**    | Política de conexão (geralmente "Default"). |

---

### 5. Guia "Security"

| Campo                          | Descrição |
|--------------------------------|-----------|
| **Microsoft Defender for SQL** | Ative proteção avançada (opcional). |
| **Encryption**                 | Transparente e habilitada por padrão (TDE). |
| **Authentication**            | Azure Active Directory, SQL Authentication ou ambos. |

---

### 6. Guia "Additional Settings"

| Campo                    | Descrição |
|--------------------------|-----------|
| **Data Source**          | Banco de dados em branco, backup existente ou amostra. |
| **Collation**            | Ordenação de texto (padrão geralmente é `SQL_Latin1_General_CP1_CI_AS`). |

---

### 7. Guia "Tags"

- Adicione tags de identificação como `Environment=Production` ou `Project=CarSalesAPI`.

---

### 8. Guia "Review + Create"

- Revise todas as configurações.
- Clique em **Create** para iniciar o provisionamento do banco de dados.

---

## Conectando-se ao Banco de Dados

Após a criação:

- Use o botão **"Set server firewall"** para permitir seu IP local.
- Conecte via:
  - **SQL Server Management Studio (SSMS)**
  - **Azure Data Studio**
  - **Aplicações (.NET, Java, etc.)**
- String de conexão disponível no portal em:  
  `SQL Database > Connection Strings`

---

## Dicas Importantes

- Mantenha o **firewall** bem configurado.
- Utilize **políticas de backup** e **retentiva de dados**.
- Configure **alertas de desempenho** e **uso de recursos**.
- Adote **autenticação via Azure AD** para maior segurança.

---

## Recursos Úteis

- [Documentação oficial - Azure SQL Database](https://learn.microsoft.com/azure/azure-sql/)
- [Ferramentas para conexão com SQL Azure](https://learn.microsoft.com/sql/azure-data-studio/)
- [Modelo de preços do Azure SQL](https://azure.microsoft.com/pricing/details/sql-database/)

