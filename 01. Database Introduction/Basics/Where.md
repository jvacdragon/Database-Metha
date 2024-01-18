Tem três formas de usar o WHERE:

EXISTEM DIVERSOS OUTROS OPERADORES LÓGICOS QUE PODEM SER USADOS COM WHERE.

* 1. Usando valores entre um e outro. Pode ser usado para datas e números por exemplo.

SELECT conlumnName
FROM tableName
WHERE columnName BETWEEN value1 AND value2;

* 2. Usando LIKE para pegar valores com certo padrão.

SELECT conlumnName
FROM tableName
WHERE columnName LIKE 'Rio%';

OBS: Nesse exemplo serão selecionados todos os dados que começam com 'Rio', independente das letras subsequentes.

* 3. Selecionar todos os valores específicos.

SELECT conlumnName
FROM tableName
WHERE columnName IN ('RJ', 'SP');

OBS: Nesse exemplo seão selecionados todos os valores que contem 'RJ' e 'SP'.