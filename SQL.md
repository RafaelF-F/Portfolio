# Portfólio

**Esse é o meu portfólio de SQL**

Em um primeiro momento quero demonstrar os aspectos fundamentais de SQL (Structured Query Language) no Microsoft SQL Server. 👨‍💻

A linguagem SQL pode ser utilizada em diversos banco de dados, como oracle, SQL Server, MySQL, BigQuery e muitos outros. Algumas funções podem variar a forma de aplicação, conforme o banco de dados que está sendo utilizado, nesse caso vou estar utilizando o SQL Server.

---
**1. Utilizando as query SELECT e FROM**: Vamos trabalhar com a tabela de vendas.

**Vou selecionar apenas a coluna vendedor dessa tabela.**

**Tabela - vendas**
|cliente|vendedor|valor 
--------|--------|-----
|1|Maria|100
|2|Ana|150
|3|Maria|200
|4|Maria|50
|5|Ana|100
|6|Ana|100

**Utilizo a seguinte query:**

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

Agora vou estar selecionando a coluna **cliente** da tabela vendas.

**Utilizo a seguinte query:**

```SQL 
SELECT cliente
FROM vendas;
```
SELECT: Para selecionar a coluna **(cliente).**

FROM: Para selecionar a tabela **(vendas).**

|resultado:|
|-----------|
|cliente|
|1|
|2|
|3|
|4|
|5|
|6|

---

**2.Selecionando dados**

Posso selecionar mais de uma coluna da tabela, para isso, basta separar os campos com uma vírgula **(,).**

**Tabela - vendas**
|cliente|vendedor|valor 
--------|--------|-----
|1|Maria|100
|2|Ana|150
|3|Maria|200
|4|Maria|50
|5|Ana|100
|6|Ana|100

**Utilizo a seguinte query:**

```SQL 
SELECT cliente, vendedor
FROM vendas;
```
SELECT: Para selecionar as colunas **(cliente, vendedor).**

FROM: Para selecionar a tabela **(vendas).**

---

Posso estar selecionando todos os campos da tabela com a seguinte query:

```SQL 
SELECT cliente, vendedor, valor
FROM vendas;
```
Mas posso estar utilizando um comando mais simples que é o **asterisco (*)**.

```SQL 
SELECT *
FROM vendas;
```

---

**3. DISTINCT: retirando as duplicidades**

**Tabela - vendas**
|cliente|vendedor|valor 
--------|--------|-----
|1|Maria|100
|2|Ana|150
|3|Maria|200
|4|Maria|50
|5|Ana|100
|6|Ana|100

Vou selecionar o campo **vendedor**, da tabela **vendas**:

**Utilizando a seguinte query:**

```SQL
SELECT vendedor
FROM vendas
```

|resultado:|
|-----------|
|vendedor|
|Maria|
|Ana|
|Maria|
|Maria|
|Ana|
|Ana|

Mas utilizando essa query, o resultado vem com vários valores repetidos.
Para evitar essa duplicidade no resultado, podemos utilizar o comando **DISTINCT (tradução: distinto).**

```SQL
SELECT DISTINCT vendedor
FROM vendas
```

|resultado:|
|-----------|
|vendedor|
|Maria|
|Ana|

Vou selecionar o campo valor, retirando as duplicidades.

```SQL
SELECT DISTINCT valor
FROM vendas;
```

|resultado:|
|-----------|
|valor|
|100|
|150|
|200|
|50|

Agora vou utilizar o comando DISTINCT, para selecionar os campos vendedor e valor, retirando as duplicidades.

```SQL
SELECT DISTINCT vendedor, valor
FROM vendas;
```
**Resultado:**
|vendedor|valor 
|--------|-----
|Maria|100
|Ana|150
|Maria|200
|Maria|50
|Ana|100

Repare que apenas a última linha foi filtrada, pois repete o mesmo valor nas duas Colunas **Ana** e **100** 

---

**4. Utilizando a query WHERE**

Quando estamos analisando dados em tabelas, é muito comum precisarmos de apenas partes das informações contidas na mesma.
Para isso, podemos filtrar esses dados que satisfazem condições específicas, através do comando **WHERE (tradução: onde).**

Vou aplicar o comando WHERE, na query abaixo.
Para isso, filtrarei apenas os registros que tiraram nota igual a 10, da tabela alunos.

**Tabela - alunos**
|nome|materia|nota 
--------|--------|-----
|Cassio|Artes|10
|Mônica|Geografia|8
|José|Geografia|6
|Bernardo|Artes|10
|Aline|Geografia|8

**Utilizando a seguinte query:**

```SQL
SELECT *
FROM alunos
WHERE nota = 10;
```

**Resultado:**
|nome|materia|nota 
--------|--------|-----
|Cassio|Artes|10
|Bernardo|Artes|10

**Vou selecionar apenas a materia = 'Geografia'.**

```SQL
SELECT *
FROM alunos
WHERE materia = 'Geografia';
```

**Resultado:**
|nome|materia|nota 
--------|--------|-----
|Mônica|Geografia|8
|José|Geografia|6
|Aline|Geografia|8
