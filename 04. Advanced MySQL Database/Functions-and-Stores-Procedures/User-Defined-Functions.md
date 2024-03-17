# User-Defined Functions

## Funções Simples

Sintaxe: 

CREATE FUNCTION functionName()
RETURNS dataType DETERMINISTIC
RETURN 

Exemplo de uso:

CREATE FUNCTION TotalCost(Cost decimal)
RETURNS decimal DETERMINISTIC
RETURN Cost - Cost*0.1

Na função acima a função recebe um parâmetro Cost do tipo DECIMAL e retorna esse valor com desconto de 10%

Para usar a função, apenas utilizar um SELECT. Exemplo: SELECT TotalCost(100);

## Funções mais complexas

Utilizar um DELIMETER para delimitar onde a função vai terminar. E usar também BEGIN e END para determinar início e fim da função. Também é possível utilizar de IF e ELSE no meio da função.

Exemplo:

DELIMITER //
CREATE FUNCTION getTotalCost(Cost decimal)
RETURNS decimal DETERMINISTIC 
BEGIN 
    IF(Cost>=100 AND Cost<500) THEN SET Cost = Cost - Cost*0.1; ELSEIF(Cost>=500) THEN SET Cost = Cost - Cost*0.2;
END IF; RETURN Cost; END //

Na função acima o Valor retornado é com desconto de 10% caso seja igual a 100 e menor que 500 e, caso valor seja igual ou maior que 500, o valor retornado é com desconto de 20%.

## Principais diferenças entre PROCEDURE e FUNCTION


* Uma função retorna um único valor, enquanto um procedimento pode retornar um único valor, múltiplos valores ou nenhum valor.

* Tipicamente, funções encapsulam fórmulas comuns ou regras genéricas de negócio que são reutilizáveis entre declarações SQL e procedimentos armazenados. Procedimentos, por outro lado, são usados principalmente para processar, manipular e modificar dados no banco de dados.

* Funções apenas aceitam parâmetros de entrada, enquanto procedimentos armazenados podem aceitar parâmetros IN, OUT e INOUT.

* Funções podem ser invocadas de qualquer lugar, incluindo declarações SELECT e procedimentos armazenados. Procedimentos armazenados são invocados usando apenas a declaração CALL.

* Uma função armazenada é criada usando a declaração CREATE FUNCTION. Um procedimento armazenado é criado usando a declaração CREATE PROCEDURE.

* Para construir uma função, você deve especificar se é uma função DETERMINISTIC ou não. Isso significa que você precisa decidir se a função sempre retorna o mesmo resultado para os mesmos parâmetros de entrada. Se você não usar DETERMINISTIC, então o MySQL usa a opção NOT DETERMINISTIC por padrão.

* Para construir funções, você deve especificar o tipo de dados do valor de retorno na declaração RETURNS. Isso pode ser qualquer tipo de dados MySQL válido. No entanto, não é necessário fazer isso com procedimentos armazenados.