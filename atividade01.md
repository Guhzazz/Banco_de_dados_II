# Lista de Exercícios 1
1 - a) Busca Linear (S1): O otimizador escolhe esse método quando não existe um índice para o campo CPF ou quando
a tabela é tão pequena que é mais rápido ler todos os dados diretamente do disco do que consultar o índice primeiro.
Ele literalmente olha linha por linha.

Índice Primário (S3a): O otimizador escolhe esse método quando o CPF é a chave primária e está indexado. O índice funciona
como o sumário de um livro: o SGBD descobre a página exata onde o CPF está e vai direto nela, sem precisar ler a tabela toda.

b) O arquivo físico da tabela FUNCIONARIO deve estar ordenado pelo campo que está sendo buscado(nesse caso, o CPF)

2 - a)O otimizador vai analisar qual das três condições (Departamento 5, Salário > 30.000 ou Sexo Feminino) retorna o menor número de linhas.
Ele escolhe usar o índice desse campo mais restritivo porque é mais eficiente carregar poucos registros para a memória do que muitos.

b) O SGBD usa o índice do atributo mais seletivo (ex: Departamento = 5) para buscar no disco apenas os funcionários desse departamento.
Uma vez que esses poucos registros são carregados na memória principal (RAM), o SGBD simplesmente testa o restante das condições
(Salario > 30000 e Sexo = 'F') linha por linha, descartando as que não passam no teste.

3 - a) Fase de ordenação: O SGBD pega o arquivo gigante, divide-o em pedaços pequenos (que caibam na memória RAM), ordena cada pedaço
individualmente e os salva de volta no disco (gerando "subarquivos" ordenados).
Fase de intercalação (Merge): O SGBD pega esses vários subarquivos menores e vai "costurando" (mesclando) as primeiras linhas de cada um,
criando arquivos cada vez maiores e já ordenados, até que reste apenas um arquivo gigante totalmente ordenado.

b) Como o arquivo não cabe todo na memória, o buffer serve como uma "área de manobra". O SGBD usa esse espaço para carregar blocos dos subarquivos
do disco, compará-los rapidamente na RAM, e ir guardando o resultado em um buffer de saída antes de gravar no disco novamente. Sem a RAM, a operação seria inviável.

4 - a)A operação de JUNÇÃO (JOIN) é a mais pesada e cara para o banco de dados. Ao fazer as seleções (filtrar linhas) e projeções (cortar colunas inúteis) antes,
enviamos a menor quantidade de dados possível para a junção, tornando-a muito mais rápida.

b) Fazer a seleção primeiro reduz drasticamente o tamanho das tabelas temporárias (arquivos intermediários) que o banco precisa criar durante a consulta. Com arquivos menores,
gasta-se menos memória RAM, menos tempo de CPU e, o mais importante, muito menos leituras e escritas no disco, reduzindo o custo total.

5 - a) O custo de uma consulta envolve tempo de CPU, uso de memória e envio de dados pela rede, mas o custo de acesso ao disco (I/O) é o maior problema. Isso porque o disco rígido (ou SSD)
é um componente físico/mecânico milhares de vezes mais lento que a CPU e a RAM. Toda vez que o banco precisa "ir ao disco" buscar um bloco, há uma perda enorme de performance.
Minimizá-las é o grande segredo.

b) Para a consulta Dnumero > 5, o SGBD consulta o índice apenas uma vez para descobrir onde começa o primeiro registro que atende à condição (ex: o departamento 6).
Como o arquivo físico já está ordenado por número de departamento, o SGBD não precisa mais usar o índice: ele simplesmente vai até aquela posição inicial no disco e lê todas
as linhas sequencialmente dali até o fim do arquivo.
