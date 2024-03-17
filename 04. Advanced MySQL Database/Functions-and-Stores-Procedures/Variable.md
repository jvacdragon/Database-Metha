# Variables
São usadas para passar valores entre querys SQL e também para passar valores entre procedures.

## Criando variáveis

@variableName = value;

### * Dentro de um procedure:
Uma variável é criada dentro de um procedure utilizando o comando SET. Exemplo:

SET @variableName = value;

ou

DECLARE variableName DATATYPE DEFAULT VALUE;

### * Dentro de um SELECT:

SELECT @variableName := value;

OU

SELECT function() INTO variableName FROM tableName;
