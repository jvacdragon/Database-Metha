# ALTER TABLE

Como o nome ja diz, esse é o comando utilizado para alterar tabelas, com ele podem ser usados os comando como MODIFY,ADD, DELETE e DROP.

## MODIFY

Comando utilizado junto com ALTER TABLE para modificar algo na tabela, como uma coluna.
Exemplo:

* ALTER TABLE tableName MODIFY columnName varchar(100) NOT NULL;

Acima estamos modificando uma coluna para que o tipo seja varchar(100) e adicionando a restrição NOT NULL.
Multiplos MODIFY podem ser utilizados em cadeia sem que seja necessária a repetição do comando ALTER TABLE.

## ADD

Também é possível adicionar colunas com o comando ADD.
Exemplo:

* ALTER TABLE tableName ADD (columnName varchar(100) NOT NULL);

Acima se está adicionando uma coluna à tabela.

## DROP

Este é o comando para basicamente deletar algo da tabela, como uma coluna por exemplo.

* ALTER TABLE tableName DROP COLUMN columnName;