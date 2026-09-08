# comandos CRUD para o banco de dados Fly By Night

```sql
--- Insert de fornecedores
INSERT INTO fornecedores (nome) VALUES('Eletrônicos Tabajara'):

INSERT INTO fornecedores (nome) VALUES
('Games ABCD'),
('Supermercado Tem de Tudo'),
('Livraria Demais da Conta');
```

## INSERT na tabela produtos

```sql
INSERT INTO produtos (nome, descricao, preco, quantidade, fornecedor_id)
VALUES(
     'Smartphone Galaxy S23',
     'Equipamento com sistema Android e camera Full HD e etc e tal',
     1599.45,
     20,
     1 -- id do fornecedor Eletrônicos Tabajara
);

INSERT INTO produtos (nome, descricao, preco, quantidade, fornecedor_id)
VALUES (
'Senhor dos Aneis: As Duas Torres',
'Volume 2 da serie de livros criados pelo autor J.R.R. Tolkien',
80.99,
100,
4 -- id do fornecedor Livraria
);

INSERT INTO produtos (nome, descricao, preco, quantidade, fornecedor_id)
VALUES(
'TV Led',
'Tela de 50 polegadas, resolucao 4K, 4 entradas HDMI e etc e tal',
3420,
12,
1 -- id do fornecedor Eletrônicos Tabajara

);
```

## Insert na tabela lojas 

```sql
INSERT INTO lojas(nome) VALUES('Casas Bahia');
INSERT INTO lojas(nome) VALUES('Shopping Zona Leste');
INSERT INTO lojas(nome) VALUES('Bazar das Coisas');
INSERT INTO lojas(nome) VALUES('Americanas');
```

## INSERT na tabela Lojas-Produtos

Esta é uma tabela intermediária (também conhecida como ** tabela
pivot ** ), ou seja, ela se relaciona com outras duas tabelas:
** produtos ** e ** lojas ** através de chaves estrangeiras.

```sql
INSERT INTO lojas_produtos(loja_id, produto_id, estoque) VALUES(2, 1, 20);



INSERT INTO lojas_produtos(loja_id, produto_id, estoque) VALUES(4, 2, 3);

INSERT INTO lojas_produtos(loja_id, produto_id, estoque) VALUES(2, 3, 10);

INSERT INTO lojas_produtos(loja_id, produto_id, estoque) VALUES(1, 1, 5);

INSERT INTO lojas_produtos(loja_id, produto_id, estoque) VALUES(4, 1, 2);
```

## UPDATE na tabela fornecedores

```sql
UPDATE fornecedores SET nome  = 'Mundo dos Games'
WHERE id = 2;
```


## UPDATE na tabela produtos


``` sql
UPDATE produtos SET preco = 2999, quantidade = 5 WHERE id = 3;
UPDATE produtos SET preco = 2999, quantidade = 5 WHERE nome = ;
```

## UPDATE na tabela lojas_produtos

``` sql
    UPDATE lojas_produtos SET estoque = 4 WHERE loja_id = 2 AND produto_id = 1;
    
    -- SQL  aceita operadores lógicos: AND (E), OR (OU), NOT (NÃO)
    -- AND -> E
    -- OR -> OU
    -- NOT -> NÃO 
```