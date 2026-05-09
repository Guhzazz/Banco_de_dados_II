# Questões - Transações

1. SImular uma conta bancária id, titular e saldo poitivo.
2. ana: 1000, Bruno: 500, Carlos: 300, Daniela: 800.
3. O saldo correspondente ao id 1 recebeu + 100 e o id 2 -100.
4. Para evitar problemas de concorrrência, caso fossem duas transações, uma com cada update, poderia haver uma falha.
5. Porque houve um rollback, logo, a transação foi completamente apagada.
6. Em situações onde existe a possibilidade de concorrência, e por consequência, suerge a possibilidade de erros como a leitura suja.
7. Para evitar o erro de saldo negativo.
8. Um erro de exceção local, já que uma regra de negócio foi violada.
9. A conta de id 4 foi debitada e as contas de id 1 e 2 foram creditadas.
10. Pela mesma ideia de evitar concorrências
11. Verificar se os dados estariam atualizados ou se teriam sido alterados.
12. Uma transação não sabe nada sobre a outra, e antes de um commit, a transação não está concluída.
13. A sessão 2 esperou até que a sessão 1 fosse finalizada para executar.
14. Porque jáhavia uma transação sendo executada na mesma conexão.
15. usado para bloquear as linhas retornadas, impedindo que outras transações as modifiquem ou bloqueiem até que a transação atual seja concluída.
16. Porque estão lidando com registros diferentes, a sessão 1 usa o id 1 e a sessão 2 usa o id 4.
17. Quando a mesma operação é feita em linhas diferentes da tabela, não há concorrência operacional.
18. Saber dados referentes às transações é importante para monitorar e corrigir possíveis erros.
19. Para garantir que a movimentação esteja com dados coerentes com as mudanças feitas nos updates
20. Occorreira um tipo de leitura suja, pois os dados estariam desconexos.
21. Garanntiu que os updates feitos dentro da transação não fossem aplicados.
22. Precisa expliar porra?
23. Verificar se as informações permanecem coerentes com as alteraçẽos feitas
24. porque bancos de dados são projetados para garantir que múltiplos passos de uma operação de negócios sejam tratados como uma única "unidade lógica de trabalho".Garantido pelas propriedades ACID.

# Questões dissertativas
25. É como uma unidade lógica de trabalho, que permite que as etapas de um processo em um banco de dados sejam tratadas como um evento único no tempo.
26. O Commit encerra uma transação que ocorreu com sucesso, criando um marco temporal desse acontecimento, já o Rollback encerra uma transação que falhou, apagando tudo que deveria acontecer nessa transação, fazendo com que "nunca tenha existido".
27. A transação bancária ilustra perfeitamente o perigo da inconsistência, se essa operação fosse tratada como comando isolados, poderia resultar em perca de dinheiro ou dinheiro aparecendo do nada.
28. O banco de dados perde a capacidade de refletir a realidade e pode gerar problemas como lost update(perca de dados por sobreposição) ou dirty read(leitura de dados inválidos).
29. Enquanto a transação é a unidade de trabalho, o ACID é o conjunto de regras que o banco de dados deve seguir rigorosamente para garantir que essa unidade de trabalho seja confiável.
30. A atomicidade é a garantia de que uma transação composta por múltiplas etapas seja tratada como uma unidade única e indivisível, ou seja, ou ela é um sucesso total, ou ela é completamente desfeita
31. Significa dizer que os dados fazem sentido lógico para o sistema, as tansações asseguram que se o banco começa em um aestado "válido" ele deve terminar em um estado igualmente "válido.
32. O isolamento é a propriedade que define como e quando as mudanças feitas por uma transação se tornam visíveis para as outras. Sem o isolamente um usuário poderia interferir acidentalmente no trabalho do outro, gerando dados inconsistentes.
33. 
