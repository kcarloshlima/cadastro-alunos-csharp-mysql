# Cadastro de Alunos — C# e MySQL

Aplicação desktop desenvolvida em **C# com Windows Forms e MySQL** para gerenciamento de estudantes, permitindo realizar operações de cadastro, consulta, atualização e exclusão de registros.

## 📋 Sobre o projeto

Este projeto foi desenvolvido como atividade prática de programação, com o objetivo de aprimorar os conhecimentos em desenvolvimento de aplicações desktop e integração com bancos de dados relacionais.

A aplicação possui uma interface gráfica que permite gerenciar as informações dos estudantes de maneira simples e organizada, utilizando o MySQL para armazenar os dados.

## ✨ Funcionalidades

- [x] Cadastro de estudantes.
- [x] Consulta e exibição dos registros em uma tabela.
- [x] Atualização dos dados cadastrados.
- [x] Exclusão de estudantes.
- [x] Seleção da data de ingresso por calendário.
- [x] Validação de campos obrigatórios.
- [x] Validação do formato do e-mail.
- [x] Verificação de e-mails duplicados.
- [x] Integração com banco de dados MySQL.
- [x] Operações assíncronas utilizando `async` e `await`.

## 🗂️ Dados cadastrados

O sistema permite armazenar as seguintes informações:

| Campo | Descrição |
|---|---|
| ID | Identificador único do estudante. |
| Nome | Nome do estudante. |
| E-mail | Endereço de e-mail. |
| Curso | Curso em que está matriculado. |
| Data de ingresso | Data de ingresso no curso. |
| Telefone | Número de telefone. |
| Cidade | Cidade de residência. |

## 🛠️ Tecnologias utilizadas

- **C#** — Linguagem de programação.
- **.NET / Windows Forms** — Desenvolvimento da aplicação desktop e interface gráfica.
- **MySQL** — Sistema gerenciador de banco de dados.
- **MySql.Data** — Biblioteca de conexão entre C# e MySQL.
- **Visual Studio / Visual Studio Code** — Ambientes de desenvolvimento.

## 📁 Estrutura do projeto

```text
ConexaoBD/
│
├── Program.cs
├── Aluno.cs
├── CadastroForm.cs
├── CadastroForm.Layout.cs
│
└── ConexaoBD.csproj
```

### Organização dos arquivos

| Arquivo | Responsabilidade |
|---|---|
| `Program.cs` | Inicialização da aplicação. |
| `Aluno.cs` | Classe que representa os estudantes e suas propriedades. |
| `CadastroForm.cs` | Lógica do sistema, validações e operações com o banco de dados. |
| `CadastroForm.Layout.cs` | Construção e organização dos componentes da interface. |
| `ConexaoBD.csproj` | Configurações e dependências do projeto. |

## 🗄️ Banco de dados

O projeto utiliza um banco de dados MySQL chamado `inscricoes`, contendo uma tabela denominada `estudante`.

### Estrutura da tabela

Execute o seguinte script SQL para criar o banco de dados e sua respectiva tabela:

```sql
CREATE DATABASE inscricoes;

USE inscricoes;

CREATE TABLE estudante (
    id INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(120) NOT NULL,
    email VARCHAR(180) NOT NULL,
    curso VARCHAR(120) NOT NULL,
    data_ingresso DATETIME NULL,
    telefone VARCHAR(11) NULL,
    cidade VARCHAR(150) NULL,
    PRIMARY KEY (id),
    UNIQUE (email)
);
```

### Configuração da conexão

No arquivo `CadastroForm.cs`, configure a string de conexão de acordo com as informações do seu ambiente MySQL:

```csharp
private const string ConnectionString =
    "Server=localhost;" +
    "Port=3306;" +
    "Database=inscricoes;" +
    "User ID=SEU_USUARIO;" +
    "Password=SUA_SENHA;";
```

> **Importante:** utilize suas próprias credenciais locais. Não publique senhas ou informações privadas de acesso ao banco de dados no repositório.

## 🚀 Como executar o projeto

### Pré-requisitos

Antes de executar a aplicação, certifique-se de possuir:

- [.NET SDK](https://dotnet.microsoft.com/download) instalado.
- [MySQL](https://dev.mysql.com/downloads/) instalado e configurado.
- Visual Studio ou Visual Studio Code.

### Passo a passo

**1. Clone o repositório:**

```bash
git clone https://github.com/kcarloshlima/cadastro-alunos-csharp-mysql.git
```

**2. Acesse a pasta do projeto:**

```bash
cd cadastro-alunos-csharp-mysql
```

**3. Abra o projeto** no Visual Studio ou Visual Studio Code, utilizando o arquivo `ConexaoBD.csproj`.

**4. Crie o banco de dados** executando o script SQL apresentado na seção anterior.

**5. Configure a conexão** com o banco de dados no arquivo `CadastroForm.cs`.

**6. Restaure as dependências:**

```bash
dotnet restore
```

**7. Execute a aplicação:**

```bash
dotnet run
```

## 🎯 Objetivos de aprendizagem

O desenvolvimento deste projeto proporcionou a prática de conceitos importantes da programação, como:

- Programação Orientada a Objetos (POO).
- Classes, propriedades e encapsulamento.
- Eventos e manipulação de componentes Windows Forms.
- Validação e tratamento de dados.
- Operações CRUD (Create, Read, Update e Delete).
- Comandos e consultas SQL.
- Integração entre aplicações C# e bancos de dados relacionais.
- Programação assíncrona com `async` e `await`.

## 📌 Status do projeto

**Concluído** — Atividade prática acadêmica.

Desenvolvido como parte dos estudos em Sistemas de Informação.
