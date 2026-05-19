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
33. DIzer que uma transação é durável significa que após o commit o banco assegura que os dados estão gravados de forma permanente e não volátil.
34. O controle de concorrência é o conjunto de regras e mecanismos que um SGBD utiliza para gerenciar a execução simultânea de várias transações. Sem o controle de concorrência, o banco de dados falharia em manter a propriedade de Isolamento do ACID.
35. O lock é o mecanismo fundamental que o banco de dados utiliza para implementar o controle de concorrência pessimista. Sua função é atuar como um "semafóro" ou "tranca", impedindo que múltiplas transações acessem ou modifiquem o mesmo dado simultaneamente de forma conflitante.
36. Vamos supor um sistema de vendas de ingresso, onde há 1 ingresso restante disponível e os usúarios, A e B, tentam comprá-lo ao mesmo tempo. Se o usuário A faz a operação de escrita primeiro sem um FOR UPDATE, o cliente B pode ler o status da disponibilidade do ingresso antes da alteração de A e constatar, erroneamente, que ele está dísponivel. Assim, no final do processo, o ingresso é vendido duas vezes, com B sobreescrevendo A.
37. O problema de atualização perdida acontece quando duas transações leêm um valor ao mesmo tempo, uma altera esse valor e salva e a outra também altera, sem considerar a alteração da primeira, e salva, sobreescrevendo a primeira alteração, como se ela nunca tivesse existido.
38. As leituras não geram problema por que não alteram o estado dos dados. 1000 usuários podem ler um dado e não haverá problema nenhum, todos vão enxergar o mesmo dado e como a leitura não altera o seu valor não haverá a incosistẽncia. Todavia, se há escrita pode haver um conflito e criar valores inconsistente, como visto na questão 37.
39. Isso é feito para garantir atomicidade, evitando que uma transação seja feita sem constar na tabela de histórico. Assim, se houver uma falha, nenhuma das duas gravações são feitas e nenhuma incosistência é gerada.
40. A matrícula de aluno é um exemplo de operação que deveria ser tratada como transação, pois é constítuida de processos que deveriam ocorrer de forma atômica (decrementar número de vagas, associar aluno a uma turma e registrar na tabela de histórico). Se feito de forma separada, pode haver falhas entre os processos e uma turma ter, por exemplo, uma vaga a menos dísponivel sem que nenhum aluno fosse associado a ela.
41. Um sistema de controle de estoque, em que o processo de decrementação em 1 unidade de um produto é feito, seguido de um registro de uma nota fiscal. Da mesma forma da questão 40, se feitos esses processos de forma separado, haverá um decréscimo no estoque sem que nenhum produto fosse de fato vendido. Se usado o rollback, caso haja falha entre os processos, é desfeito qualquer operação pertencente à operação.
42. O processamento de transações contribui para a confiabilidade do sistema se apoiando nos quatro princípios básicos ACID.
43. Para entender como esses conceitos funcionam de forma conjunta, é necessário entender que o objetivo final do banco de dados é a consistẽncia, mas essa só pode ser garantida com os conceitos de atomicidade e isolamento, que evitam valores incosistentes. Esses dois últimos também dependem um do outro para garantir estados consistente: se a atomicidade estiver implementada e uma transação sofrer rollback, embora todas as alterações tenham sido desfeitas, uma outra transição, pela falta de isolamento, pode ler o valor alterado (que posteriormente não foi efetivado) e passar adiante essa incosistência. E por fim, a durabilidade serve para pegar esse estado consistente gerado e garantir que ele irá perdurar, mesmo que uma bomba caia no servidor, usando logs de operações e algoritmos de restauração.
