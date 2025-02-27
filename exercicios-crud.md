## exercicios crud

```sql
INSERT INTO generos(nome) VALUES('terror'),('suspense'),('fantasia'),('ação');

INSERT INTO filmes(titulo, lancamento, genero_id)
VALUES(
      'Haireiser',
      '1990-07-06',
      1;
),
(
   'Ilha do medo',
   '2010-03-12',
   2

),
(
   'Historia sem fim',
   '1984-10-05',
   3
),
(
    'Maquina Mortifera',
    '1987-05-28',
    4
);

INSERT INTO detalhes(duracao,sinopse,bilheteria,orcamento,filme_id)
VALUES(
    94,
    'No Marrocos, Frank Cotton, um hedonista, compra uma bela e intrincada caixa de quebra-cabeça mística, conhecida como Configuração do Lamento, que supostamente abre um portal para um reino de prazer sobrenatural',
    14600000.00,
    1000000.00,
    1

),
(
    139,
    'Em 1954, os agentes federais dos Estados Unidos, Edward "Teddy" Daniels e seu novo parceiro Chuck Aule viajam para o Hospital Ashecliffe para os criminosos insanos em Shutter Island, no Boston Harbor. Eles estão investigando o desaparecimento da paciente Rachel Solando, encarcerada por afogar seus três filhos.',
    80000000.00,
    28400000.00,
    2
),
(
    107,
    'Bastian Balthazar Bux (Barret Oliver) é um garoto sonhador, que usa a imaginação como refúgio para os fatos que o entristecem, como as provas de Matemática, brigas na escola e, especialmente, a recente perda de sua mãe. Um dia, o garoto a caminho da escola briga com outros colegas, foge, e acaba parando numa livraria, onde toma conhecimento de um livro chamado "A História Sem Fim". ',
    100000000.00  ,
    85000000.00,  
    3
),
(
    110,
    'Um detetive famoso por sua ousadia e sangue frio e um pacato e tranquilo policial que está a espera da aposentadoria se juntam em uma missão para desbaratar uma quadrilha internacional de traficantes de drogas composta por ex-militares da guerra do Vietnã, que eram membros da CIA, liderados pelo ex-General Peter MacAllister ',
    15000000.00,
    120207127.00,
    4

);
 DELETE FROM detalhes WHERE id = 5;
 DELETE FROM detalhes WHERE id = 6;
 DELETE FROM detalhes WHERE id = 7;
 DELETE FROM detalhes WHERE id = 8;

 UPDATE detalhes SET bilheteria= 14600000.00 , orcamento = 1000000.00
where id = 1;

 UPDATE detalhes SET bilheteria= 80000000.00 , orcamento = 28400000.00
where id = 2;

 UPDATE detalhes SET bilheteria= 100000000.00  , orcamento = 85000000.00
where id = 3;

 UPDATE detalhes SET bilheteria= 150000000.00 , orcamento = 120207127.00
where id = 4;

SELECT titulo , lancamento, genero_id FROM filmes
WHERE id IN (2,4);

```