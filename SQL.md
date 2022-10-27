# Portfólio

**Esse é o meu portfólio de SQL**

Em um primeiro momento quero demonstrar os aspectos fundamentais de SQL (Structured Query Language) no Microsoft SQL Server. 👨‍💻

A linguagem SQL pode ser utilizada em diversos banco de dados, como oracle, SQL Server, MySQL, BigQuery e muitos outros. Algumas funções podem variar a forma de aplicação, conforme o banco de dados que está sendo utilizado, nesse caso vou estar utilizando o SQL Server.

---
**1. Utilizando os comandos SELECT e FROM**: Vamos trabalhar com a tabela de vendas.

**Vou selecionar apenas a coluna vendedor dessa tabela.**

**Tabela - vendas**
|cliente|vendedor|valor 
--------|--------|-----
|1|Maria|100
|2|Ana|150
|3|Maria|200
|4|Maria|50
|5|Ana|100

**Utilizo o seguinte comando:**

```SQL 
SELECT vendedor
FROM vendas;
```
SELECT: Para selecionar a coluna **(vendedor).**

FROM: Para selecionar a tabela **(vendas).**

Não é obrigatório, mas é considerada uma boa prática, finalizar uma query de SQL com ponto e vírgula **(;)**.

|resultado:|
|-----------|
 |vendedor|
 |Maria|
 |Ana|
 |Maria|
 |Maria|
 |Ana|

Agora vou estar selecionando o campo cliente da tabela vendas.

**Utilizo o seguinte comando:**

```SQL 
SELECT cliente
FROM vendas;
```
SELECT: Para selecionar a coluna **(cliente).**

FROM: Para selecionar a tabela **(vendas).**

---

**2.Selecionando dados**

Posso selecionar mais de uma coluna da tabela, para isso, basta separar os campos com uma vírgula (,).

**Tabela - vendas**
|cliente|vendedor|valor 
--------|--------|-----
|1|Maria|100
|2|Ana|150
|3|Maria|200
|4|Maria|50
|5|Ana|100

Utilizo o seguinte código:

```SQL 
SELECT cliente, vendedor
FROM vendas;
```
SELECT: Para selecionar as colunas **(cliente, vendedor).**

FROM: Para selecionar a tabela **(vendas).**

---

Posso estar selecionando todos os campos da tabela com o seguinte código:

```SQL 
SELECT cliente, vendedor, valor
FROM vendas;
```
Mas posso estar utilizando um comando mais simples que é o **asterisco (*)**.

```SQL 
SELECT *
FROM vendas;
```
