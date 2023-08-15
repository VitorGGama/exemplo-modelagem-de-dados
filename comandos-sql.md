# Comandos SQL - Referências

## Modelagem fisica com comandos DDL

### criar banco de dados

CREATE DATABASE vendas CHARACTER SET utf8mb4;

### Criar tabela de fabricantes

```sql

CREATE TABLE fabricantes (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```

### Visualizar detalhes estruturais da tabela

```sql
DESC fabricantes;
```
### Criar tabela de produtos

```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENTE, 
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(500) NULL,
    preco DECIMAL  (6,2) NOT NULL,
    fabricante_id INT NOT NULL
);

```

### Criação do relacionamento entre as tabelas (chave estrangeira)

```sql
ALTER TABLE produtos 
    --CONSTRAINT/RENDIÇÃO indicando o nome do relacionamento
    ADD CONSTRAINT  fk_produtos_fabricantes
    FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id);   

    --Criando a chave-estrangeira (fabricante_id) que 
    --aponta para a chave-prímaria (id) de outra tabela(fabricantes) 


```





