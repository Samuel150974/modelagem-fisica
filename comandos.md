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