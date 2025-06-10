# AcademiaCRUD

Sistema simples em Java para gerenciamento de alunos e treinos em uma academia, com funcionalidades de cadastro, listagem, atualização e exclusão (CRUD). Utiliza JDBC para conexão com banco de dados e interface via terminal.

## Pré-requisitos

- Java 
- Maven 
- Banco de dados MySQL xampp
- IDE como netbeans o qual foi usado

## Configuração do Banco de Dados

Crie um banco de dados no MySQL:

```sql
CREATE DATABASE academia;
```

Crie as tabelas necessárias:

```sql
CREATE TABLE aluno (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    cpf VARCHAR(14),
    data_nascimento DATE,
    telefone VARCHAR(20),
    email VARCHAR(100)
);

CREATE TABLE treino (
    id INT PRIMARY KEY AUTO_INCREMENT,
    aluno_id INT,
    data_inicio DATE,
    descricao TEXT,
    duracao_minutos INT,
    tipo_treino VARCHAR(50),
    FOREIGN KEY (aluno_id) REFERENCES aluno(id)
);
```

## Configuração do Projeto

1. Clone ou extraia o projeto.
2. Configure o arquivo de conexão JDBC (ex: `Conexao.java`) com os dados do seu banco (URL, usuário, senha).
3. Compile com Maven:

```bash
mvn compile
```

4. Execute:

```bash
mvn exec:java -Dexec.mainClass="trabalho.academiacrud.Main"

## Funcionalidades

-  Cadastrar Aluno
-  Listar Alunos
-  Cadastrar Treino
-  Listar Treinos por Aluno
-  Atualizar Treino
-  Deletar Treino

## Estrutura do Projeto

```
AcademiaCRUD/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── trabalho/academiacrud/Main.java
│   │   │   ├── dao/AlunoDAO.java
│   │   │   ├── dao/TreinoDAO.java
│   │   │   ├── model/Aluno.java
│   │   │   └── model/Treino.java
│   │   └── resources/
├── pom.xml
└── README.md
```

## Autor

Felipe de Souza
Gabriel de Oliveira de Souza