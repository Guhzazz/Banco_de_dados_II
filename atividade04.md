# Questões transações

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
16. 
