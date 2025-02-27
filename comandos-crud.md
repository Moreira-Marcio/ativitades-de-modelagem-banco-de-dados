# Comandos para operações CRUD no Banco de Dados

## Resumo

- C -> **C**reate   -> **INSERT**: inserir dados/registros na tabela
- R -> **R**ead     -> **SELECT**: consultar/ler dados/registros na tabela
- U -> **U**pdate   -> **UPDATE**: atualizar dados/registros na tabela
- D -> **D**elete   -> **DELETE**: excluir dados/registros na tabela

---

## INSERT (Fabricantes)

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) VALUES('Apple');

INSERT INTO fabricantes (nome) VALUES('LG'), ('Samsung'), ('Brastemp');
```

## SELECT (Fabricantes)

```sql
SELECT * FROM fabricantes;
```
## Produtos

```sql
INSERT INTO produtos(nome,descricao,preco,quantidade,fabricante_id)
VALUES('ultrabook','equipamento de ultima geração cheio de recursos, e etc e tal...',3999.45,
7,2--id do fabicante dell
);
INSERT INTO produtos(nome,descricao,preco,quantidade,fabricante_id)
VALUES('tablet androide','tablet versão 16 do sistema operacional androide, possui tela de 10 polegadas e armazenamento de 128 gb ',900,
12,5
);

INSERT INTO produtos(nome,descricao,preco,quantidade,fabricante_id)
VALUES(
    'geladeira',
    'Refrigeradpr frost-free com acesso a internet',
    5000,
    12,
    6
),
(
    'iphone 18 pro max ferradão',
    'Smartphone apple cheio das frescuras e caro pra caramba',
    9666.66,
    3,
    3
),
(
    'ipad mini',
    'tablet apple com tela retina display e bla bla bla',
    4999.99,
    5,
    3
);

```
## comandos do exercicio

```sql
INSERT INTO fabricantes (nome) VALUES('Microsoft'),('Positivo');

INSERT INTO produtos(nome,descricao,preco,quantidade,fabricante_id)
VALUES (
    'Xbox Series S',
    'Velocidade e desempenho de última geração',
    1997,
    5,
    7
),
(
    'Notebook Motion',
    'Intel Dual Core 4GB de RAM, 128GB SSD e Tela 14,1 polegadas',
    1213.65,
    8,
    8

);

```
---

## SELECT (Produtos)

```sql
-- Lendo TODAS as colunas de TODOS os registros
SELECT * FROM produtos;

-- Lendo somente nome e preco de todos os registros
SELECT nome, preco FROM produtos;
SELECT preco, nome FROM produtos;

-- Mostrar nome, preco e quantidade SOMENTE dos produtos que custam abaixo de 5000
SELECT nome, preco, quantidade FROM produtos
WHERE preco < 5000;

-- Mini-exercício: mostre o nome e descrição somente dos produtos da Apple

SELECT nome,descricao FROM produtos
WHERE fabricante_id = 3;

```

### operadores logicos: e , ou, não

### e (and)

```sql

--exibir nome e preço dos produtos que custão entre 2000 e 6000
SELECT nome,preco FROM produtos
WHERE preco >= 2000 and preco <=6000;

```

### ou (or)

```sql

---exibir nome preço descrição dos produtos apple e samsung
SELECT nome, preco,descricao FROM produtos
where fabricante_id = 5 or fabricante_id = 3;

--- função usando sql IN 
SELECT nome, descricao FROM produtos
WHERE fabricante_id IN (3,5);
```

### operador não (not)

```sql
--- nome,descrição e preço de todos os produtoas exeto da positino
SELECT nome,descricao,preco FROM produtos
WHERE NOT fabricante_id =8;

---versão usando operador relacional de diferença
SELECT nome,descricao,preco FROM produtos
WHERE fabricante_id !=8;
```

### UPDATE (fabricantes)

```sql

UPDATE fabricantes SET nome = 'Asus do Brasil'
WHERE id =1;

--- alterar as quantidade para 10 dos produtos que custão a baixo de 2000 exeto microssoft
UPDATE produtos SET quantidade= 10
WHERE preco < 2000 AND fabricante_id != 7;
---WHERE preco < 2000 AND NOT fabricante_id = 7

UPDATE produtos SET quantidade = 5
where id = 6;

```

### delete (fabricantes e produtos)

#### ☠️ perigo  
#### sempre use a clausula where

```sql
DELETE FROM fabricantes where id = 4;
DELETE FROM fabricantes where id = 1;

DELETE FROM produtos WHERE id = 4;
DELETE FROM fabricantes where id = 3;


```

## classificação/ordenação



```sql
SELECT nome, preco FROM produtos ORDER BY nome;
SELECT nome, preco FROM produtos ORDER BY preco;
SELECT nome, preco FROM produtos ORDER BY preco DESC;

SELECT nome, preco, quantidade FROM produtos 
WHERE fabricante_id = 5 ORDER BY quantidade;
```

### operações funções de agregação


```sql
SELECT SUM(preco) FROM produtos;

SELECT SUM(preco) AS total FROM produtos; --- (as) alias/apelido pra coluna
SELECT SUM(preco) AS "total dos preços dos produtos"FROM produtos;
SELECT FORMAT (SUM(preco),2) AS total FROM produtos;
SELECT REPLACE(FORMAT(SUM(preco),2),",",".") AS total FROM produtos;

SELECT nome AS produto, preco as preço FROM produtos;
SELECT nome  produto, preco  preço FROM produtos;

--função de media: avg

SELECT AVG(preco) AS "média dos preços" FROM produtos;
SELECT ROUND(AVG(preco),2) AS "média dos preços" FROM produtos;

--função de contagem
SELECT COUNT(id) AS "Quantidade de produtos" FROM produtos;
SELECT COUNT(DISTINCT fabricante_id) AS "Quantidade de fabricantes com produtos" FROM produtos;


-- operaçõe smatematicas

SELECT nome,preco,quantidade, (preco*quantidade) AS total FROM produtos;



```