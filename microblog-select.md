

## Consultas Básicas
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

## Filtros com WHERE


```sql
SELECT * FROM usuarios WHERE tipo_usuario = editor;
```

```sql
SELECT * FROM noticias WHERE destaque = 'sim';
```

```sql
SELECT * FROM noticias WHERE id_categoria = 3;
```

```sql
SELECT * FROM noticias WHERE id_usuario <> 4;
```

## Combinando condições

Faça uma consulta utilizando AND para estabelecer duas condições simultaneamente.

```sql
SELECT titulo, resumo FROM noticias
WHERE id_categoria < 6 AND id_usuario > 1;

A lógica está certa, porém dependendo do numero id de condições não trará resultados
```

```sql
SELECT titulo, texto, resumo, destaque FROM noticias
WHERE id_categoria > 3 OR id_usuario > 4;
```

## Pesquisas com LIKE

```sql
SELECT titulo,resumo FROM noticias WHERE titulo LIKE '%O Novo%';

```
Faça uma consulta utilizando LIKE para encontrar registros cujo texto comece com determinada letra ou palavra.

```sql
SELECT * FROM noticias WHERE
 titulo LIKE '%tecnologia%' OR
 texto LIKE '%tecnologia%' OR
 resumo LIKE '%tecnologia%' OR
imagem LIKE '%tecnologia%';
```

## Ordenação

```sql
SELECT titulo, data FROM noticias ORDER BY data;
```

```sql
SELECT nome FROM usuarios ORDER BY nome;
```

## Funções de agregação

```sql
SELECT COUNT(*) AS total_usuarios
FROM usuarios;

SELECT COUNT(*) AS total_noticias
FROM noticias;

SELECT MIN(data) AS data_antiga, MAX(data) AS data_atual FROM noticias;


```

## Desafio

```sql
SELECT titulo AS noticia, data AS publicacao FROM noticias
 
 ```



## Comandos aleatorios
```sql
UPDATE noticias 
SET data = NOW() - INTERVAL FLOOR(RAND() * 180) DAY - INTERVAL FLOOR(RAND() * 86400) SECOND;

```