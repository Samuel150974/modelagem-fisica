``` sql
CREATE DATABASE microblog CHARACTER SET uft8mb4;

```

```sql
CREATE TABLE categoria(
            id INT NOT NULL,
            nome VARCHAR(100) NOT NULL 
);
```
```sql
CREATE TABLE usuario(
            id INT NOT NULL AUTO_INCREMENT,
            nome VARCHAR (100) NOT NULL,
            email VARCHAR(150) UNIQUE NOT NULL,
            senha VARCHAR(255) NOT NULL,
            tipo_usuario ENUM('admin','editor') NOT NULL

);
```

```sql
CREATE TABLE noticia(
            id INT NOT NULL,
            nome VARCHAR(200) NOT NULL,
            reumo VARCHAR (500) NOT NULL,
            texto_completo TEXT NOT NULL,
            nome_imagem VARCHAR(100) NOT NULL,
            data_publicaca DATE_TIME NOT NULL,
            destaque ENUM('sim','nao') NOT NULL,
            id_usuario INT NOT NULL,
            id_categoria INT NOT NULL



);
```