# Trigger

Um TRIGGER é usado para disparar uma função ou procedure sempre que uma determinada ação ocorrer no bando de dados.
Como criar: 

CREATE TRIGGER triggerName
TRIGGER TYPE
ON tableName FOR EACH ROW
BEGIN
    statementOne
    statementTwo
    ...
END

Para deletar um TRIGGER a query é:
DROP TRIGGER IF EXISTS schemaName.triggerName;

## Tipos de TRIGGERS

Existem 3 principais tipos: INSERT TRIGGER, UPDATE TRIGGER, DELETE TRIGGER. Eles podem ocorrer antes(BEFORE) ou depois(AFTER) de uma dessas ações ocorrer. Exemplo:

CREATE TRIGGER triggerName
BEFORE DELETE
ON tableName FOR EACH ROW
BEGIN
    logic
END
