# exercicios de SQL

## Criar banco

```sql

CREATE DATABASE catalogo_de_filmes CHARACTER SET utf8mb4 ;

```

## Criar tabelas: Gêneros, filmes e detalhes

```sql

CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY  AUTO_INCREMENT,
    nome VARCHAR(45)NOT NULL
);

```

```sql

CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY  AUTO_INCREMENT,
    titulo VARCHAR(200)NOT NULL,
    lancamento DATE NOT NULL,
    genero_id INT NOT NULL -- SERA UMA CHAVE ESTRANGEIRA (FK)
);

```


```sql

CREATE TABLE detalhes(
    id INT NOT NULL PRIMARY KEY  AUTO_INCREMENT,
    duracao INT NOT NULL,
    sinopse  TEXT(1000) NOT NULL,
    bilheteria DECIMAL (16,2)NULL,
    orcamento DECIMAL (16,2)NULL,
    filme_id INT NOT NULL --FK

);

```

## Alterando as tabelas e configurando as chaves estrangeiras(fks)

```sql
ALTER TABLE filmes
   ADD CONSTRAINT fk_filmes_generos
   FOREIGN KEY(genero_id)REFERENCES generos(id);

```

```sql
ALTER TABLE detalhes
   ADD CONSTRAINT fk_detalhes_filmes
   FOREIGN KEY(filme_id)REFERENCES filmes(id);

```

