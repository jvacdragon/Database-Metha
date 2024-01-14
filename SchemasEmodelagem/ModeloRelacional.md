# O que é o modelo relacional?

É um modelo construído em torno de três principais conceitos:

* Dado
* Relações
* Constraints

É um jeito de organizar e guardar dados em um banco de dados. Definindo os dados que serão utilizados, seus tipos e relações entre as tabelas.

# Domínio

É o tipo de dado que uma coluna da tabela aceita, sendo do tipo numérico, texto, etc.

# Grau

Grau é o número de colunas que uma tabela tem. Uma tabela que contém id, nome, numeroTelefone, email seria uma tabela de grau 4.

# Cardinalidade

Quantidade de linhas/records que uma tabela tem salvo.

# Tipos de relacionamentos entre tabelas

## 1. One-to-one (1:1)

Relação que siginifica que para cada record na tabela X, existirá apenas um record na tabela Y.
Um exemplo seria considerar duas tabelas, uma de País e outra de Capital. Cada país tem apenas uma capital e cada Capital está relacionada à apenas um país.

## 2. One-to-many (1:N)

Neste caso, é a relação onde uma tabela X está relacionada à diversas tabelas Y enquanto cada tabela Y está relacionada à apenas uma tabela X.
Continuando o exemplo de país, e considerando uma tabela estado, um record da tabela país pode estar relacionado à diversas tabelas estao, mas cada record da tabela estado pode apenas se relacionar com uma tabela país.

## 3. Many-to-many (N:N)

Aqui, duas tabelas se relacionam de forma que tabela X pode ter relação com diversas tabelas Y e vice-versa. Um bom exemplo seria uma tabela Cliente que tem relação com uma tabela Produto. Um cliente pode comprar diversos produtos enquanto um produto pode ser vendido para diversos clientes.
Normalmente esse tipo de relação não é colocada dessa forma em um modelo de dados. O padrão é criar uma tabela entre elas que se relaciona de forma one-to-many com as duas tabelas.