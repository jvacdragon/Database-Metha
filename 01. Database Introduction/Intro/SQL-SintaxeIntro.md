* Criar banco de dados:
CREATE DATABASE database_name;

* Criar tabela: 
CREATE TABLE table_name (column_name1 datatype(size), column_name2 datatype(size), column_name3 datatype(size))

* Adicionar colunas com valores na tabela:
INSERT INTO table_name (column_one, column_two, column_three, ...) VALUES (value1, value2, value3, ...);

* Atualizer dados de tabela:
UPDATE  table_name SET column_name = new_value WHERE column_contains_PK = PK_value;

* Deletar dado:
DELETE FROM table_name WHERE column_contains_PK = PK_value;

* Deletar tabela:
DROP TABLE table_name;

* Selecionar dados:
SELECT column_name, other_column_name, ... FROM table_name WHERE column_name = some_value;

* Criar coluna na tabela: 
ALTER TABLE table_name ADD (column_name datatype(size));

* Criar chave primária na tabela:
ALTER TABLE table_name ADD primary key (column_name);

* Remover todos os dados de uma tabela
TRUNCATE TABLE table_name;
