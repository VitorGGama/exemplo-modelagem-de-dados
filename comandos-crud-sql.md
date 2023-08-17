# Comandos para operações CRUD no banco de dados

## Resumo 

C -> CREATE (inserir dados usando comando `INSERT`)
R -> READ (ler dados usando comando `SELECT`)
U -> UPDATE(atualizar dados usando comando `UPDATE`)
D -> DELETE(excluir dados usando comando `DELETE`)

## INSERT

### Fabricantes 

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');

```


```sql
INSERT INTO fabricantes (nome) VALUES('Dell');

INSERT INTO fabricantes (nome) VALUES('Aplle');

INSERT INTO fabricantes (nome) VALUES('LG'), ('Sansung'), ('Brastemp');

INSERT INTO fabricantes (nome) VALUES('Positivo'), ('Microsoft');

```
### Produtos

```sql
INSERT INTO produtos (nome, preco, descricao, quantidade, fabricante_id)
VALUES(
    'Ultrabook', 
    3500,
    'equipamento de ultima geração cheio de recursos, com processador Intel
    Core i9 show de bola.',
    7,
    2 --id do fabricante DELL

);

INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id)
VALUES(
    'Tablet android',     
    'Tablet com a versão 14 do sistema operacional android, possui tela 
    de 10 polegadas e armazenamneto de 128 GB, e 64 GB de Ram',
    1500.99,
    5,
    5
);



INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id)
VALUES(
    'Geladeira',     
    'refrigerador fros-free com acesso a internet',
    5000,
    12,
    6
);
(
    'iphone 18 Pro Max',
    'Smartphone Aplle cheio das frescuras e caro de mais',
    12666.6,
    3,
    3
);

(
    'ipad Mini',
    'Tablet Aplle com tela retina display e tals',
    4999.01,
    5,
    3
)



INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id)
VALUES
(
    'Xbox Series S',
    'Velocidade e desempenho de ultíma geração',
    1997,
    5,
    8
);

INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id)
VALUES
(
'Notebool Motion',
'Intel dual core 4GB de RAM, 128GB SSD e tela 14,1 Polegadadas',
1213.65,
8,
7
);

```
## Select 

```sql
SELECT * FROM produtos;

SELECT nome, preco FROM produtos;

SELECT preco, nome FROM produtos;

SELECT nome, preco, quantidade FROM produtos WHERE preco < 5000;

SELECT nome, descricao  FROM produtos WHERE fabricante_id = 3 ;

```
## Operadores Lógicos: E, OU, NÃO
## E
```sql
SELECT nome, preco FROM produtos
WHERE preco >= 2000 AND preco <= 6000; 

-- A query abaixo não retorna registros
-- já que as condições não foram totalmente atendidas
SELECT nome, preco FROM produtos
WHERE preco > 5000 AND preco <= 6000; 
```

## OU
```sql
SELECT nome, preco FROM produtos
WHERE preco > 5000 OR preco <= 3000; 

-- Exiba nome e preço somente dos produtos
-- da Apple e da Samsung
SELECT nome, preco FROM produtos
WHERE fabricante_id = 3 OR fabricante_id = 5;

-- versão usando a função IN()
SELECT nome, preco FROM produtos
WHERE fabricante_id IN(3, 5);

SELECT nome, preco FROM produtos
WHERE fabricante_id NOT IN(3, 5);

``` 

## NÃO
```sql
SELECT nome, descricao, preco FROM produtos
WHERE NOT fabricante_id = 8;

-- versão usando operador relacional "diferença/diferente"
SELECT nome, descricao, preco FROM produtos
WHERE fabricante_id != 8;

```

## UPDATE



```sql
--ATUALIZAR -> UPDATE
--CONFIGURAÇÃO -> SET
--ONDE -> WHERE

UPDATE fabricantes SET nome = 'Asus do Brasil'
WHERE id = 1; -- não se esqueça do WHERE!!
```

```sql
UPDATE produtos SET preco = 6549.74
WHERE id = 4;
```

```sql
UPDATE produtos SET quantidade = 20 WHERE fabricante_id IN (3, 5);
```

## DELETE

```sql
DELETE FROM fabricantes WHERE id = 1;

DELETE FROM fabricantes WHERE id = 4;

--A query abaixo NÃO FUNCIONA devido á restrição
-- de chave estrangeira/relacionamento, ou seja,
--existem produtos associados ao fabricante 3 (aplle)
--DELETE FROM fabricantes WHERE id = 3;

```

## SELECT: outras formas de uso

```sql
SELECT nome, preco FROM produtos ORDER BY nome;
SELECT nome, preco FROM produtos ORDER BY preco;

SELECT nome, preco FROM produtos ORDER BY preco DESC;

--DESC: Classificação em ordem decrescente
--ASC (padrão): classificação em ordem crescente


```







