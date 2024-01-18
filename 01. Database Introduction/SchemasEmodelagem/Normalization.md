# O que é normalização de dados?

A normalização de dados é uma forma de padronizar a forma como se cria tabelas e e divide os ados entre as tabelas, visando diminuir problemas como duplicação de dados, erros, e simplificar queries do banco de dados.

# 1. Primeira forma normal (1NF)

A primeira forma normal tem os seguintes critérios:

* Cada célula da tabela deve conter apenas um valor (atomicidade)
* A tabela deve ter uma chave primária para identificação única de cada registro.
* Não pode haver duplicação de linhas ou colunas.
* Cada coluna deve ter apenas um valor para cada registro na tabela.

# 2. Segunda forma normal (2NF)

Na segunda forma normal se deve evitar dependências parciais de relacionamentos entre tabelas. Dependência parcial se refere à tabelas que tem chaves primárias compostas. Considere a tabela de pacientes a seguir que simula um hospital.

| patientID | patientName |  slotID | totalCost |
| --------- | ----------- | ------- | --------- |
| 1         |     joao    | A1      |    1500   |
| 2         |     pedro   | A2      |    1800   |
| 3         |    eduardo  | A2      |    2000   |

Para evitar algo desse tipo, nesse caso devemos dividir em duas tabelas. Primeiro uma de paciente, contendo apenas o ID e o nome do paciente.

| patientID | patientName |
| --------- | ----------- |
| 1         |     joao    |
| 2         |     pedro   |
| 3         |    eduardo  |

E por fim é preciso criar uma tabela para marcação, com um ID para que cada record na tabela seja único, essa forma eliminando a dependência parcial que existia na primeira tabela criada.

| appointmentID | slotID | totalCost |
| ------------- | ------ | --------- |
|       1       | A1     |    1500   |
|       2       | A2     |    1800   |
|       3       | A2     |    2000   |


# 3. Terceira forma normal (3NF)

Para que as relações de banco de dados estejam na terceira forma, é necessário que ja estejam na segunda forma.

<img src="https://hermes.dio.me/assets/articles/956a313e-8b82-42b3-a810-391cae386235.png">

Nesta tabela, se tem informações sobre os funcionários, como ID, nome e cargo, bem como informações sobre o departamento ao qual estão vinculados, incluindo o ID, nome e localização do departamento.

Agora, para atender à Terceira Forma Normal (3FN), deve-se remover as colunas que possuam valores que podem ser obtidos a partir da combinação de valores de outras colunas na mesma tabela.

Nesse caso, podemos identificar que as colunas "Nome_Departamento" e "Localizacao_Departamento" são funcionalmente dependentes do atributo "ID_Departamento". Ou seja, o nome e a localização do departamento podem ser obtidos a partir do ID do departamento.

Para alcançar a 3FN, deve-se criar uma nova tabela para armazenar as informações sobre os departamentos separadamente, removendo essas informações da tabela "Funcionario". Além disso, precisamos adicionar uma chave primária à nova tabela "Departamento".

<img src="https://hermes.dio.me/assets/articles/ddbe36b4-d3e9-482b-883e-18c0192624dc.png">

Após a normalização, essa será a tabela funcionários:

<img src="https://hermes.dio.me/assets/articles/a4c7636d-fa54-44cf-9416-99a7ee155742.png">

Dessa forma, alcançamos a Terceira Forma Normal (3FN). A tabela "Funcionario" agora não possui informações redundantes sobre o nome e a localização do departamento, pois esses detalhes estão armazenados na tabela "Departamento" e são referenciados pelo ID do departamento na tabela "Funcionario". Isso ajuda a evitar a redundância de dados e a garantir a consistência e a integridade das informações no banco de dados.