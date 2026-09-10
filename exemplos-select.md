# SQL SELECT - Exemplos de consultas ao banco Fly By Night

O comando `SELECT` é usado para **Consultar dados amrzenados nas tabelas do banco de dados**.

##SELECT básico

consultar todos os dados de uma tabela:
## SELECT báscico: consultar todos os dados de uma tabela:                                                         
```sql
SELECT * FROM produtos;
```

## SELECT apenas para determinadas colunas

``` SQL
SELECT nome, preco FROM produtos;
 ```

 ## Alterando o nome de exibição das colunas

 Usamos o comando `AS` para criar um ** apelido (alias)**.

 ``` sql
 SELECT
     nome AS produto,
     preco AS valor

     FROM produtos;

 ``` 

 ## Filtrando registros com WHERE

 O `WHERE` permite determinar **quais registros devem aparecer** no resultado. Na prática, são condições para execução do `SELECT`.

 ### Comparação de igualdade

 ```sql
 SELECT * FROM produtos WHERE quantidade = 0;
 ```

### Comparação de maior

```sql
SELECT nome, preco FROM produtos WHERE preco > 1000;
```
 ### Comparação de menor ou igual

```sql
SELECT nome, preco FROM produtos WHERE preco <= 100;
```

### Comparação de diferença

Normalmente se usa o operador `<>` em vez do `!=`;

```sql
SELECT * FROM produtos WHERE fornecedor_id <> 1;
```

## Combinando condições

Usamos o `WHERE` e operadores lógicos e relacionais.

## OPERADOR AND (E)

Exibir os produtos que custem menos de 500 e quantidade acima de 20.

```sql
SELECT nome, preco, quantidade FROM produtos
WHERE preco < 500 AND quantidade > 20;
```

### Operador OR (OU)

Exibir os produtos que custem mais de 3000 ou com quantidade zerada.

```sql
SELECT nome, preco, quantidade FROM produtos
WHERE preco > 3000 OR quantidade = 0;
```

### Operador NOT (NÃO)

Exibir os produtos que **não possuem preço acima de 1000**

```sql
SELECT nome, preco FROM produtos WHERE NOT preco > 1000;
```

**OBS.:** o uso do `NOT` não é obrigatório, desde que você consiga o mesmo resultado usando uma lógica diferente, como no exemplo:

`SELECT nome, preco FROM produtos WHERE preco <= 1000;`

### BETWEEN

Exibir produtos com preço **Entre 100 e 500**

```sql
SELECT nome, preco FROM produtos
WHERE preco BETWEEN 100 AND 500;
```

## OPERADOR IN

Exibir produtos que tenham o fornecedor ID 1, 4 ou 8.
```sql
SELECT * FROM produtos
WHERE fornecedor_id IN (1, 4, 8);

```

Sem usar o  `IN`, teríamos que fazer a lógica com múltiplos `OR`:

```sql
SELECT * FROM produtos
WHERE
fornecedor_id = 1 OR
fornecedor_id = 4 OR
fornecedor_id = 8; 
```


### LIKE
 
`LIKE` é usado principalmente para realizar pesquisas em textos. Junto com o caractere `%` permite fazer buscas baseadas em partes de uma string.
 
Exemplo: procurar produtos que tenham a palavra **Gamer** em qualquer posição do nome.
 
```sql
SELECT nome, preco FROM produtos
WHERE nome LIKE '%Gamer%';
```
 
## DISTINCT
 
Elimina valores repetidos do resultado da consulta.
 
```sql
SELECT DISTINCT fornecedor_id FROM produtos
```
 
## ORDENAÇÃO (ou CLASSIFICAÇÃO)
 
Usamos o `ORDER BY` para organizar os registros do resultado.
 
### Ordem crescente (padrão)
 
Exemplos: do menor para o maior, ou de A-Z, de mais antigo para mais recente.
 
```sql
SELECT nome, preco FROM produtos
ORDER BY preco ASC;
-- nem precisa colocar o ASC, pois é padrão
```
 
### Ordem decrescente
 
 Exemplos: do maior para o menor, ou de Z-A, ou do mais recente
 para o mais antigo.

 ```sql
SELECT nome, preco FROM produtos
ORDER BY preco DESC;
 ```

 ### Ordenando por mais de uma coluna

 ```sql
SELECT nome, preco FROM produtos
ORDER BY preco DESC, nome ASC;
 ```


## Funções de agregação

Funções de agregações realizam cálculos ou processos em registros de um resultado.

Entre as principais:

- `COUNT ()` -> conta com registros
- `SUM ()` -> soma valores
- `AVG ()` -> calcula a média de valores
- `MIN()` -> encontra o menor valor
- `MAX()` -> encontra o maior valor
- `ROUND()` -> arredonda valores e define casas decimais

### COUNT

Contando quantos registros existem na tabela produtos:

```sql
SELECT COUNT (*) AS total FROM produtos;
```

## SUM (somar)

Soma quantidade de todos os produtos da tabela:

```sql
SELECT SUM(quantidade) AS "Quantidade Total " FROM produtos;
```

## AVG

Calcular a média dos preços dos produtos:

```sql
SELECT AVG(preco) AS "Média dos Preços " FROM produtos;
```

## MIN

Retornar o menor preço existente:

```sql
SELECT MIN(preco) AS menor_preco FROM produtos;

```

## MAX

Retornar o maior preço existente:

```sql
SELECT MAX(preco) AS maior_preco FROM produtos;

```


## Combinando agregações

```sql
SELECT

COUNT(*) AS quantidade_produtos,
MIN(preco) AS menor_preco,
MAX(preco) AS maior_preco,
ROUND(AVG(preco), 2) AS preco_medio
FROM produtos;

```

```sql

```