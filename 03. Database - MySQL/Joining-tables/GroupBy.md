# Funções Agregadoras

São as funções: SUM(), MIN(), MAX(), COUNT(), AVG()

# GROUP BY

GROUP BY é normalmente usado com funções agregadores. Ele agrupa linhas das tabelas que tem o mesmo valor. Um exemplo de uso seria algo do tipo "Quantas pessoas neste banco de dados moram no mesmo endereço?". Para responder à esta pergunta, uma possível query pode ser: 

* SELECT COUNT(id), adress FROM person GROUP BY adress;

Acima a query irá agrupar os resultados em uma tabela, onde para cada endereço diferente da tabela será retornado um linha e ao lado do endereço estará a quantidade de pessoas (verificaas pelo count(id)) que tem o endereço registrado a elas.

# HAVING

Funciona como um WHERE, mas que ao invés de definir condições a nível de dados, define a nível de linha, para filtrar as linhas que serão mostrada no output de uma query que utilila GROUP BY.

Exemplo:

* SELECT Department, SUM(orderTotal) AS totalOrdens FROM orders GROUP BY Department HAVING totalOrdens > 2000;

Acima, a query retorna cada departamento mostrando ao lado o valor de soma de todas as colunas orderTotal  de cada departamento. No entanto, ela exclui de mostrar todos os departamentos onde a soma de oderTotal é menor que 2000.