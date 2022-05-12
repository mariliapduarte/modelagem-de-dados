# Comandos CRUD SQL

## Resumo da sigla
- C create - comando SQL é INSERT
- R read - comando SQL é SELECT
- U update - comando SQL é UPDATE
- D delete - comando SQL é DELETE

## INSERT

INSERT INTO fabricantes(nome) VALUES('Asus');
INSERT INTO fabricantes(nome) VALUES('Dell');
INSERT INTO fabricantes(nome) VALUES('Apple');
INSERT INTO fabricantes(nome) VALUES('LG');

INSERT INTO fabricantes(nome)
VALUES('Samsung'), ('Microsoft'), ('Brastemp');



INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id)
VALUES('TV Led', 2000, 5, 'TV de última geração', 6);

INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id)
VALUES('iPhone', 5500.79, 8, 'Smartphone caro para caramba', 4);



INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id) VALUES
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    8 -- Brastemp 
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.',
    4 -- Apple
),
(
    'Xbox',
    2500,
    6,
    'Console de última geração com acesso aos melhores jogos e bla bla',
    7 -- Microsoft
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',
    1 -- Asus
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    7 -- Microsoft
),
(
    'Tablet Android',
    4999,
    3,
    'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB.',
    6 -- Samsung
);


## SELECT
SELECT nome, preco FROM produtos;

SELECT nome, preco FROM produtos WHERE preco < 3000;

SELECT nome, preco FROM produtos 
WHERE preco < 3000 AND preco > 2000;

SELECT nome, preco FROM produtos 
WHERE fabricante_id = 3 OR fabricante_id = 1;

## ordenando a busca
SELECT nome, descricao FROM produtos
ORDer by nome DESC; -- decrescente

SELECT nome, descricao FROM produtos
ORDER by preco DESC; -- decrescente

SELECT 
    produtos.nome, 
    fabricantes.nome,
    produtos.preco, 
    produtos.quantidade
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id;
