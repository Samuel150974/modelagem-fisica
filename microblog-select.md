```sql
SELECT *FROM usuarios;
```

```sql
SELECT nome, email FROM usuarios;
```

```sql
SELECT categorias;
``` 

```sql
SELECT titulo, data FROM noticias;
```

```sql
SELECT 
nome AS usuario,
tipo_usuario AS funcao_usuario

FROM usuarios;
```

```sql
SELECT * FROM usuarios WHERE tipo_usuario = editor;
```

```sql
SELECT * FROM noticias WHERE destaque = 'sim';
```

```sql
SELECT * FROM noticias WHERE nome (1)  ;
```

## Comandos aleatorios

UPDATE noticias 
SET data = NOW() - INTERVAL FLOOR(RAND() * 180) DAY - INTERVAL FLOOR(RAND() * 86400) SECOND;