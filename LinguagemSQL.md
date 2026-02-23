# Aula 1: Introdução e Fundamentos de Bancos de Dados

## 1. Introdução à Linguagem SQL

### O que é SQL?
* **SQL** significa Linguagem de Consulta Estruturada (frequentemente pronunciado como *SeQuel*).
* É a linguagem padrão utilizada para interagir com dados armazenados em bancos de dados, permitindo que os usuários realizem desde consultas simples até cálculos complexos em grandes conjuntos de dados (ex: encontrar o "Gasto Total").

### Por que aprender SQL?
* **Falar com Dados**: Permite a comunicação direta com os sistemas de dados.
* **Alta Demanda**: É uma habilidade muito requisitada no mercado de trabalho em diversas funções técnicas.
* **Caminhos de Carreira**: Conhecimento essencial para Desenvolvedores de Software, Analistas de Dados, Cientistas de Dados e Engenheiros de Dados.
* **Padrão da Indústria**: Funciona em conjunto com as principais ferramentas do mercado, como Power BI, Tableau, Kafka, Spark e Synapse.

---

## 2. Sistemas de Gerenciamento de Banco de Dados (DBMS)

Um DBMS atua como a interface entre o usuário e o banco de dados.
* **Hospedagem**: Normalmente, os bancos de dados são hospedados em servidores físicos ou na nuvem.
* **Disponibilidade**: Funcionam 24/7 para garantir o acesso ininterrupto aos dados.
* **Interação**: Aplicativos (APPs), ferramentas de BI (como Power BI) e usuários enviam consultas SQL ao DBMS para recuperar e gerenciar os dados.

### Tipos de Bancos de Dados


* **Relacional**
  * Microsoft SQL Server, MySQL, PostgreSQL, Amazon Redshift 
* **Documento**
  *  MongoDB 
* **Grafo**
  *  Neo4j 
* **Chave-Valor**
  *  Redis, Amazon DynamoDB 
* **Base de Coluna**
  *  Apache Cassandra 

--------------------------------------------------------------------------------

# Estrutura Relacional

## 3. Estrutura de um Banco de Dados Relacional

Os bancos de dados relacionais seguem uma organização hierárquica rigorosa:
1. **Servidor**: O host principal que contém um ou mais bancos de dados.
2. **Banco de Dados**: O contêiner de alto nível para os dados (ex: "Vendas" ou "RH").
3. **Esquema (Schema)**: Agrupamentos lógicos dentro de um banco de dados (ex: "Pedidos" ou "Clientes").
4. **Tabela**: Onde os dados são fisicamente armazenados em linhas e colunas.

### Componentes de uma Tabela
* **Colunas**: Categorias verticais que definem os tipos de dados.
* **Linhas**: Registros horizontais individuais.
* **Célula**: Unidade única de dado na interseção exata de uma linha com uma coluna.
* **Chave Primária**: O identificador único para cada registro dentro da tabela.
* **Armazenamento**: As tabelas são armazenadas no disco físico como arquivos de banco de dados.

### Principais Tipos de Dados
O SQL utiliza tipos de dados específicos para delimitar o formato da informação que pode ser armazenada:
* **Numéricos**: 
  * `INT` – Números inteiros.
  * `DECIMAL` – Valores numéricos com frações.
* **Texto/String**:
  * `CHAR` – Strings de comprimento fixo.
  * `VARCHAR` – Strings de comprimento variável.
* **Data & Hora**:
  * `DATE` – Formato `YYYY-MM-DD`.
  * `TIME` – Formato `HH:MM:SS`.


--------------------------------------------------------------------------------

# Aula 2.1: Tipos de Comandos SQL

## 2. Tipos de Comandos SQL

A linguagem SQL é dividida em subconjuntos com base na finalidade dos comandos:

* **DDL (Linguagem de Definição de Dados)**: Define ou modifica a estrutura do banco. 
  * CREATE – Criar novos bancos de dados ou tabelas.
  * ALTER – Modificar a estrutura existente.
  * DROP – Deletar um banco ou tabela. 
  
* **DQL (Linguagem de Consulta de Dados)**: Recupera os dados armazenados.
  * SELECT – O comando principal para buscar dados. 
 
* **DML (Linguagem de Manipulação de Dados)**: Gerencia os dados nas tabelas.
  * INSERT – Adicionar novos registros.
  * UPDATE – Modificar registros existentes.
  * DELETE – Remover registros. 
 
* **DCL (Linguagem de Controle de Dados)**: Gerencia permissões e acessos dos usuários.  
  * GRANT – Concede privilégios de acesso.
  * REVOKE – Revoga privilégios. 
  
* **TCL (Linguagem de Controle de Transações)**: Gerencia transações para garantir integridade.  
  * COMMIT – Salva mudanças permanentemente.
  * ROLLBACK – Desfaz mudanças se ocorrer um erro.
  * SAVEPOINT – Define um ponto para rollback parcial. 
 

--------------------------------------------------------------------------------
# Aula 2.2: Aprofundamento em DDL (Data Definition Language)

O **DDL** é a categoria de comandos usada para definir e criar o "esqueleto" (a planta estrutural ou *blueprint*) dos objetos do banco de dados. 

## Ações Principais do DDL:

### 1. CREATE (Criando Objetos)
Usado para construir novos bancos de dados ou tabelas do zero. Ao criar uma tabela, é obrigatório definir as colunas e seus respectivos tipos de dados.
```sql
-- Criando um Banco de Dados
CREATE DATABASE Venda;

-- Criando uma Tabela
CREATE TABLE Produto (
    ProdutoID INT,
    ProdutoName VARCHAR(100),
    Preco DECIMAL
);
2. ALTER (Modificando Objetos)
Utilizado para atualizar a estrutura de um objeto já existente (ex: adicionar ou remover colunas) sem precisar excluir a tabela inteira e perder os dados.
-- Adicionando uma nova coluna
ALTER TABLE Produto
ADD Categoria VARCHAR(50);

-- Removendo uma coluna existente
ALTER TABLE Produto
DROP COLUMN Preco;
3. DROP (Excluindo Objetos)
O comando DROP tem caráter destrutivo. Ele remove permanentemente toda a estrutura do objeto e todos os registros armazenados nele.
-- Excluindo a tabela permanentemente
DROP TABLE Produto;
```
--------------------------------------------------------------------------------
### Resumo de DDL


* CREATE
  * **Ação**: Construir novo
  * **Objeto Afetado**: Afetado: Banco de Dados, Tabela, Schema

* ALTER
  * **Ação**: Modificar existente
  * **Objeto Afetado**: Colunas, Tipos de Dados

* DROP
  * **Ação**: Excluir permanentemente
  * **Objeto Afetado**: Afetado: Banco de Dados, Tabela, Schema
