# Comandos SQL para Modelagem Física

## Criar banco da dados
CREAT DATABASE vendas_marilia CHARACTER SET utf8mb4; <!-- CHARACTER SET utf8mb4 deve ser sempre configurado! -->

## Curiosidade (desnecessário): Entrar no banco de dados criado;
USE DATABASE vendas_marilia;

## Criar tabela fabricantes
CREATE TABLE fabricantes(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,  <!-- nome do campo, tipo de dados, nulo ou não, auto incrementado ou não, chave primária -->
    nome VARCHAR(45) NOT NULL
);

CREATE TABLE produtos(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
    preco DECIMAL(8,2) NOT NULL,
    quantidade TINYINT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricante_id INT,
);

<!-- para relacionar as tabelas -->
## Alterando a tabela para criar um relacionamento por meio da chave estrangeira

ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes <!-- este nome foi retirado do workbench é o nome da FK (foreign key) -->
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);



