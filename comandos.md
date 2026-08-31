# Referência de comandos SQL para Modelagem Física


``` sql
CREATE DATABASE flybynight CHARACTER SET uft8mb4;

```

# Criação da tabela fornecedor

```sql
CREATE TABLE fornecedores(
            id INT PRIMARY KEY AUTO_INCREMENT,
            nome VARCHAR(100) NOT NULL
);
```




# Criação da tabela produtos

``` sql
CREATE TABLE produtos (
     id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
     nome VARCHAR(100) NOT NULL,
     descricao TEXT, -- como é opcional, colocamos NULL ou omitimos
     preco DECIMAL(10,2) NOT NULL, 
     quantidade INT NOT NULL,
     fornecedor_id INT NOT NULL,

     -- Configurando a chave estrangeira fornecedor_id
     -- que se conecta (referencia) a chave primária id na tabela fornecedores
     FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)
);
```
# Criação da tabela lojas

```sql
CREATE TABLE lojas(
            id INT PRIMARY KEY AUTO_INCREMENT,
            nome VARCHAR(100) NOT NULL
);
```

## Criação da tabela lojas_produtos

Nesta tabela, é necessário definir **dois relacionamentos**, um apontando para **produtos** e outro apontando para **lojas**
```sql
CREATE TABLE lojas_produtos(
         loja_id INT NOT NULL,
         produto_id INT NOT NULL,
         estoque INT NOT NULL,
        
        -- Definindo a chave primária COMPOSTA
         PRIMARY KEY (loja_id, produto_id),
         
         -- Criando as FKs apontando para as PKs de cada tabela

        -- Regras para consistência nas operações de estoque 
        -- 1) Se uma loja for excluída, os estoques dela também serão.

         FOREIGN KEY (loja_id) REFERENCES lojas (id) ON DELETE CASCADE,
         
         -- 2) Ao tentar excluir um produto, o banco deve impedir a exclusão
         FOREIGN KEY (produto_id) REFERENCES produtos (id) ON DELETE RESTRICT

        
 ); 
```