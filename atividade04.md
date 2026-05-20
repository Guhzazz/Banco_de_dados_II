# Atividade Prática

1. Precisamos saber o estado anterior e estático dos dados para verificar como o sistema lida com acessos e escritas simultâneas.
2. Para verificar se o estado é consistente após transações concorrentes, é essencial que se parta de um estado também consistente.
3. Ela foi bloqueada temporiariamente e esperou a transição 1 terminar, liberando o acesso para a linha de id = 1.
4. por que foi utilizada uma tranca para evitar corropimento de dados pela transição 1. A transação 2 só poderá acessar aquela linha de dados quando a 1 terminar e dr commit ou roolback.
5. O For update serve para trancar o acesso para escrita ja na parte de leitura, evitando que outra transição leia o valor antes da atualização e acabe sobreescrevendo depois a mudança.
6. Por que elas acessam diferentes linhas de dados, não havendo concorrência.
7. Revela que o sgbd faz o bloqueio no menor nível (em linha) para evitar gargalos em concorrência em grandes intervalos.
8. Ver se há o isolamento adequado que evita leitura suja. Se houver, a transação 2 não vai ver a alteração enquanto a 1 não der commit.
9. Ele se conecta com isolamento vendo até onde as alterações de uma transação afetam outras que acessam as mesmas linhas de dados.
10. Depende se o sgbd utilizado usa o nível de isolamento leitura repetível ou maior. Se sim, o valor permaneceu o mesmo (caso do MySQL), caso contrário não.
11. Esse teste busca identificar o fenômeno de leitura não-repetível, onde um valor lido por uma transação pode ou não ser mudado durante o fluxo da mesma.
12. por que elas manipulam os mesmos dados ao mesmo tempo, sendo possível haver inconsistências e valores inválidos que não haveriam numa serialização.
13. Pode haver o fenômeno de de atualização perdida, onde uma transição sobrescreve a alteração da outra.
14. é possível notar o bloqueio por que não há mensagem de sucesso, sem a possibilidade de executar novos comandos, pois fica em estado de espera.
15. por que ao liberar o lock ao fim da transação, isso garante que a outra transação vai fazer a nova alteração em cima do valor atualizado.
16. por que já havia um bloqueio feito pela outra.
17. Na select comum, não há há bloqueio da linha do registro. Com for update, a transação ja demonstra interesse de escrever na etapa de leitura e tranca para evitar valores inconsistentes.
18. Seria 700.
19. porque para ambas as transações tudo ocorreu certo como se elas tivessem ocorrido e tido efeito no banco de dados, mas é como se a T1 nunca tivesse ocorrido.
20. Por que os sgbd implementam bloqueio à nível de linha.
21. Que se não houvesse disputa pelo mesmo registro, o SGBD lidaria bem melhor com vários acessos simultâneos, por que o verdadeiro gargalo é a disputa pelos mesmos recursos.
22. Se um bloqueio for mantido por muito tempo, formará-se um fila de espera de transações que querem alterar aquela linha de dados bloqueado, gerando gargalo.
23. por que elas seguram as travas de segurança por muito tempo, até acabarem.
24. Refazendo as operações que constam no log de operações e vendo se os dados batem matematicamente.
25. É importante para ver se houve algum dado incosistente em decorrẽncia de um algoritmo inadequado de isolamento e tratamento de concorrẽncia.

# Atividade dissertativa

26. A concorrência acontece quando duas ou mais transações tentam acessar uma linha de registro ao mesmo instante de tempo.
27. Os bloqueios servem para garantir consistência na alteração de dados e isolamento, de forma que múltiplos acessos e alterações ao mesmo recurso, se implementadas com bloqueio, tem um output similar ao feito de forma serial.
28. Enquanto acessar registros iguais ao mesmo tempo gera disputa e concorrência, acessar registro diferentes podem ser feitos de forma paralela sem um afetar o outro.
29. por que ele não abre brechas para leituras indesejáveis na lacuna entra a leitura e a atualização de fato, o que não ocorre no select comum.
30. Significa que uma transação estava modificando uma linha de dados e impôs uma tranca áquela linha, a qual só vai ser liberada quando a transação finalizar, liberando o acesso á linha para as transações em espera.
31. Atualização perdida ocorre quando duas transações fazem uma atualização á mesma linha de dados e pelo menos uma delas é sobrescrita pela outra, de forma que o valor final reflete uma alteração só e não duas.
32. O isolamento em sistemas multiusuário é essencial para evitar que transações leiam valores instáveis e incosistentes de outras e façam mudanças em cima disso, além de garantir que os valores não irão mudar no meio de uma transação crítica.
33. Se há a leitura de um dado alterado por uma transação ainda não concluída, corre-se o risco que esta sofra rollback e a leitura, que talvez seja usada para tomar decisões, tenha se baseado num dado que não era nem de fato válido.
34. = resposta 23
35. Sem o isolamento, falhas como leitura suja e atualização perdida podem acontecer, afetando a consistência dos dados.
36. uma loja virtual em que dois clientes compram o mesmo item ao mesmo tempo. Haverá uma disputa para decrementar a quantidade desse item da tabela de estoque.
37. Pode ser que as operações simultâneas não manipulam a mesma linha, não havendo possibilidade de conflito.
38. O banco de dados implementam níveis de isolamento e técnicas otimistas para evitar o corrompimento.
39. Poderia haver um erro de consistẽncia em que duas transações decidem tirar o dinheiro de uma conta baseado no saldo atual. Para decidir se elas vão decrementar ou não, precisam ver se isso não gerará valores negativos (que fazem parte da regra do negócio). Como elas lêem sem travas, é possível que haja um decremento duplo que desrespeite a regra de negócio e o saldo da conta fica negativo.
40. Observar a ordem de execução é importante porque os problemas de concorrência são condições de corrida que dependem estritamente do tempo. Mapear o momento exato de cada comando é essencial para conseguir reproduzir o teste, já que inverter a sequência das operações muda totalmente o resultado final do banco e impede a validação correta dos bloqueios (locks) entre as sessões.

# Atividade integrada

41. A concorrência representa o desafio do sistema, que é gerenciar múltiplos usuários acessando os mesmos dados simultaneamente. Para evitar o caos desse cenário, o isolamento atua como a diretriz estratégica, definindo o nível de visibilidade que uma transação tem sobre as alterações ainda não confirmadas das outras. Na prática, esse isolamento é assegurado pelos bloqueios (locks), os mecanismos operacionais que travam registros temporariamente e forçam filas de espera quando há disputa direta por escrita, garantindo que as operações concorrentes ocorram de forma ordenada, segura e sem gerar anomalias na base de dados.
