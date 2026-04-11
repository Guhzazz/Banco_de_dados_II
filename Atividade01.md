# Aula dia 07/04

1 - select * from matricula

2 - select nome, curso from aluno

3 - select * from aluno where curso = 'Computacao'

4 - select * from aluno where cidade = 'Maringa'

5 - select * from aluno order by nome

6 - select * from aluno order by ano_ingresso

7 - select * from aluno where ano_ingresso >= 2022

8 - select * from aluno where nome like 'A%'

9 - select * from aluno where curso = 'Computacao' or curso = 'Engenharia'

10 - select * from disciplina where carga_horaria > 60 and carga_horaria < 80

11 - select count(*) from aluno

12 - select AVG(nota) from matricula

13 - select max(nota) from matricula

14 - select min(nota) from matricula

15 - select SUM(carga_horaria) from disciplina

16 - select curso, count(*) from aluno group by curso

17 - select cidade, count(*) from aluno group by cidade

18 - select situacao, AVG(nota) from matricula group by situacao

19 - select semestre, count(*) from matricula group by semestre

20 - select curso, count() from aluno group by curso having count() > 1

21 - select nome, situacao from aluno join matricula on (aluno.id = matricula.aluno_id);

22 - select a.nome , d.nome
    from aluno as a JOIN disciplina as d on(a.id = d.id);

23 - select a.nome, d.nome, m.nota
from matricula as m join disciplina as d join aluno as a 
ON(m.aluno_id = a.id and d.id = m.disciplina_id);

24 - SELECT *
from aluno a 
join matricula m on a.id = m.aluno_id
join disciplina d on m.disciplina_id = d.id
where d.departamento = 'Computacao'

25 - select distinct a.nome
from aluno a
join matricula m on a.id = m.aluno_id
where situacao = 'Reprovado'

26 - select a.nome, d.nome
from aluno a
join matricula m on a.id = m.aluno_id
join disciplina d on m.disciplina_id = d.id
where curso = 'Computacao';

27 - select a.nome, AVG(m.nota) as media_notas 
from aluno a
join matricula m on a.id = m.aluno_id
GROUP BY a.id, a.nome

28 - select a.nome, count(m.disciplina_id) as total_disciplinas
from aluno a
join matricula m on a.id = m.aluno_id
GROUP BY a.id, a.nome

29 - select a.nome, AVG(m.nota) as media_final
from aluno a 
join matricula m on a.id = m.aluno_id
group by a.id, a.nome
having AVG(m.nota) > 8;

30 - select d.departamento, count(m.id) as total_matriculas
from disciplina d 
join matricula m on d.id = m.disciplina_id
group by d.departamento
order by total_matriculas
