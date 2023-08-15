## Criando banco de dados 
### Catalogo de filmes e generos

```sql
CREATE DATABASE catalogo de filmes CHARACTER SET utf8mb4;

```

```sql
CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    genero VARCHAR(40) NOT NULL
);
```
```sql
CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT, 
    filme VARCHAR(45) NOT NULL,
    ano_de_lancamento YEAR(4) NULL,
    genero_do_filme VARCHAR(45) NOT NULL
);

```

```sql
ALTER TABLE filmes 
    ADD genero_id INT NOT NULL ; 

```


```sql
ALTER TABLE filmes
    ADD CONSTRAINT  fk_filmes_genero
    FOREIGN KEY (genero_id) REFERENCES genero(id); 

```




```sql

CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    filmes VARCHAR(40) NOT NULL
);

```