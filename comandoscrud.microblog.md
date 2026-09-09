# Comandos CRUD para o Microblog

## INSERT na tabela usuários

Ana Silva, ana@email.com, senha: 123abc, tipo: editor
Bruno Souza, bruno@email.com, senha: abc456, tipo: admin
Carla Mendes, carla@email.com, senha: 789xyz, tipo: editor

``` sql
INSERT INTO usuarios(nome, email, senha,tipo_usuario); VALUES
('Ana Silva', 'ana@email.com', '123abc', 'editor'),
('Carla Mendes','carla@email.com','789xyz','admin');


```
### INSERT na tabela categorias


``` sql


INSERT INTO categorias (nome) VALUES
('Tecnologia'),
('Entreterimento'),
('Educação');



```
### INSERT na tabela noticias
``` sql
INSERT INTO noticias (titulo, resumo, texto, imagem, destaque, id_usuario, id_categoria) VALUES ( 'Corinthians está mau pra caramba', 'O time caiu muito após a copa do mundo','Não sei mais o que escrever sobre isso tudo etc', 'corinthians.jpg', 'nao', 3, 3 );

INSERT INTO noticias (titulo, resumo, texto, imagem, destaque, id_usuario, id_categoria) VALUES ( 'Senac prepara novos títulos para 2027', 'Em 2027 diversos títulos com bolsas de estudos serão lançados','Um texto qualquer sobre esta noticia', 'cursos.png', 'sim', 1, 2 );

( 'Corinthians está mau pra caramba', 'O time caiu muito após a copa do mundo','Não sei mais o que escrever sobre isso tudo etc', 'corinthians.jpg', 'nao', 3, 3 );

```

```sql
INSERT INTO noticias (titulo, resumo, texto, imagem, destaque, id_usuario, id_categoria) VALUES ( 'Concorrência para presidência em 2026 está grande', 'Em 2026 expira o cargo de candidatos da eleição passada','Um texto qualquer sobre esta noticia', 'eleição.png', 'sim', 2, 3 );

```