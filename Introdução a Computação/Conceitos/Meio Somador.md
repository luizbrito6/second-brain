zPara entender esse conceitos é necessário primeiro compreender a soma de binários:

- 0 + 0 = 0 
- 0 + 1 = 1
- 1 + 0 = 0 
- 1 + 1 = 10 (nesse caso entra em  atividade a saída "vai um")

| A   | B   | SOMA  | VAI UM |
| --- | --- | ----- | ------ |
| 0   | 0   | 0     | 0      |
| 0   | 1   | **1** | 0      |
| 1   | 0   | **1** | 0      |
| 1   | 1   | 0     | **1**  |

Certo, após montar a tabela verdade é necessário entender o funcionamento dos bits para resultar nas saídas positivas esperadas: 

- A negado  / B normal 
- A normal / B negado 
- A normal / B normal 

Com isso conseguimos 

