``` sql
CREATE DATABASE microblog CHARACTER SET uft8mb4;

```

```sql
CREATE TABLE categorias(
            id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
            nome VARCHAR(100) NOT NULL 
            
);
```
```sql
CREATE TABLE usuarios(
            id INT NOT NULL AUTO_INCREMENT,
            PRIMARY KEY (id),
            nome VARCHAR (100) NOT NULL,
            email VARCHAR(150) UNIQUE NOT NULL,
            senha VARCHAR(255) NOT NULL,
            tipo_usuario ENUM('admin','editor') NOT NULL,
            
);
```

```sql
CREATE TABLE noticias(
            id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
            titulo VARCHAR (100) NOT NULL,
            nome VARCHAR(200) NOT NULL,
            resumo VARCHAR (500) NOT NULL,
            texto_completo TEXT NOT NULL,
            nome_imagem VARCHAR(100) NOT NULL,
            destaque ENUM('sim','nao') NOT NULL,
            data_publicacao DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
            CREATE TABLE noticias (data_publicacao DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP);
            -- Nomeclatura recomendada
            -- nometabelasingular_nomecolunapk
           usuario _id INT NOT NULL,
           categoria_id INT NOT NULL

          -- Cria relacionamentos e chave estrangeira (FK)
        --   Caso um usuário ou categoria seja excluído, as notícias ficarão setadas como null 
        -- ou seja 

           FOREIGN KEY (categoria_id) REFERENCES categorias(id) ON DELETE SET NULL,
           FOREIGN KEY (usuario_id) REFERENCES usuarios(id) ON DELETE SET NULL


-- Adição de elementos em tabelas e colunas existentes

--   ALTER TABLE usuarios ADD CONSTRAINT noticias FOREIGN KEY (usuarios_id) REFERENCES usuarios (id) ON DELETE CASCADE ON UPDATE CASCADE;
--  ALTER TABLE categorias ADD CONSTRAINT noticias FOREIGN KEY (categorias_id) REFERENCES categorias(id) ON DELETE CASCADE ON UPDATE CASCADE;

);
```

