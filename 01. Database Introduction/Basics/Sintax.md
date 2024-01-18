* Selecionar todas as colunas de determinada tabela

SELECT * from tableName;

* Copiar todos os dados de uma coluna em determinada tabela para outra coluna de outra tabela

INSERT INTO tabelaAlvo(colunaAlvo)
SELECT colunaCopiar
FROM tabelaTransferencia

* Adicionar dados à uma tabela

INSERT INTO tableName(column1, column2, ...)
VALUES (value1, value2, ...);

* Trocar valores de uma linha da na tabela

UPDATE tableName 
SET columnName = newValue, columnName2 = newValue2, ...
WHERE columnName = columnValue;

* Deletar uma linha da tabela

DELETE FROM tableName WHERE columnName = columnValue;

* Deletar todas as linhas de uma tabela

DELETE FROM tableName;