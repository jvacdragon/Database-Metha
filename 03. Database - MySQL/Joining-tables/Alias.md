# Mudando nome de uma coluna no Select

* SELECT columnName AS novoNome FROM tableName;

Também é possível concatenar colunas criando uma coluna com outro nome. Exemplo:

* SELECT CONCAT(columnName1, " ", columnName2) AS novoNome FROM tableName;

No segundo argumento de CONCAT é possível escrever o que voce quer que apareça entre os valores das colunas selecionadas. Nesse caso foi colocado um espaço entre os valores.

Selecionar colunas de múltiplas tabelas dentro do banco de dados:

* SELECT x.columnName, y.columnName FROM tablemName1 AS x, tableName2 AS y;

Uma forma de utilizar em conjunto CONCAT e seleção de múltiplas tabelas é:

* SELECT CONCAT (x.name, " " ,y.name) AS "nomes_iguais" from person AS x, person2 AS y WHERE x.name = y.name;

Acima é possível verificar os valores iguais de uma coluna chamada name em duas tabelas, person e person2.