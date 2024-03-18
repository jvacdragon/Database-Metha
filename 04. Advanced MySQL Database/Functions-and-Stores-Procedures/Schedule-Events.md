Sintaxe:

CREATE EVENT [IF NOT EXISTS] eventName
ON SCHEDULE scheduleLogic
DO
eventBody

Exemplo:

CREATE EVENT GenerateRevenueReport
ON SCHEDULE AT CURRENT_TIMESTAMP + INTERVAL 12 HOUR
DO
BEGIN
    INSERT INTO reportData(orderID,clientID,productID,quantity,cost,date)
    SELECT * FROM Orders WHERE date BETWEEN "2022-08-01" AND "2022-08-31";
END

A função acima ocorrerá apenas uma vez, 12 horas após o horário atual.


CREATE EVENT GenerateRevenueReport
ON SCHEDULE 
EVERY 3 DAY
DO
BEGIN
    DELETE FROM tableName
END

Acima a cada 3 dias serão deletados os dados da tabela, repetidamente a cada 3 dias sempre.

Para deleta o evento basta usar: DROP EVENT [IF EXISTS] eventName;