# Control-Flow

Uma função de controle de flow vem da seguinte forma:

SELECT id, nomeProduto, 
CASE
    WHEN vendas < 1000 THEN "Baixa"
    WHEN vendas < 2000 AND vendas > 1000 THEN "Média"
    ELSE "Alta"
END AS volumeVendas
FROM produto;

Nessas função será retornada 3 colunas, sendo elas: id, nomeProduto e volumeVendas. O valor de volumeVendas será definido pelo bloco CASE. Caso não Exista um ELSE no final do bloco CASE e o valor não parar em nenhum WHEN, o resultado retornado será NULL.