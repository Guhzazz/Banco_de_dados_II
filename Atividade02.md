# Aula dia 07/04

## 1
```sql
select * from matricula;
```

## 3
```sql
select nome, curso from aluno;
```

## 4
```sql
select * from aluno where curso = 'Computacao';
```

## 5
```sql
select * from aluno where cidade = 'Maringa';
```

## 6
```sql
select * from aluno order by nome;
```

## 7
```sql
select * from aluno order by ano_ingresso;
```

## 8
```sql
select * from aluno where ano_ingresso >= 2022;
```

## 9
```sql
select * from aluno where nome like 'A%';
```

## 10
```sql
select * from aluno
where curso = 'Computacao' or curso = 'Engenharia';
```

## 11
```sql
select * from disciplina
where carga_horaria > 60 and carga_horaria < 80;
```

## 12
```sql
select count(*) from aluno;
```

## 13
```sql
select avg(nota) from matricula;
```

## 14
```sql
select max(nota) from matricula;
```

## 15
```sql
select min(nota) from matricula;
```

## 16
```sql
select sum(carga_horaria) from disciplina;
```

## 17
```sql
select curso, count(*)
from aluno
group by curso;
```

## 18
```sql
select cidade, count(*)
from aluno
group by cidade;
```

## 19
```sql
select situacao, avg(nota)
from matricula
group by situacao;
```

## 20
```sql
select semestre, count(*)
from matricula
group by semestre;
```

## 21
```sql
select curso, count(*)
from aluno
group by curso
having count(*) > 1;
```

## 22
```sql
select nome, situacao
from aluno
join matricula on aluno.id = matricula.aluno_id;
```

## 22 (segunda versão)
```sql
select a.nome, d.nome
from aluno as a
join disciplina as d on a.id = d.id;
```

## 23
```sql
select a.nome, d.nome, m.nota
from matricula as m
join disciplina as d
join aluno as a
on (m.aluno_id = a.id and d.id = m.disciplina_id);
```

## 24
```sql
select *
from aluno a
join matricula m on a.id = m.aluno_id
join disciplina d on m.disciplina_id = d.id
where d.departamento = 'Computacao';
```

## 25
```sql
select distinct a.nome
from aluno a
join matricula m on a.id = m.aluno_id
where situacao = 'Reprovado';
```

## 26
```sql
select a.nome, d.nome
from aluno a
join matricula m on a.id = m.aluno_id
join disciplina d on m.disciplina_id = d.id
where curso = 'Computacao';
```

## 27
```sql
select a.nome, avg(m.nota) as media_notas
from aluno a
join matricula m on a.id = m.aluno_id
group by a.id, a.nome;
```

## 28
```sql
select a.nome, count(m.disciplina_id) as total_disciplinas
from aluno a
join matricula m on a.id = m.aluno_id
group by a.id, a.nome;
```

## 29
```sql
select a.nome, avg(m.nota) as media_final
from aluno a
join matricula m on a.id = m.aluno_id
group by a.id, a.nome
having avg(m.nota) > 8;
```

## 30
```sql
select d.departamento, count(m.id) as total_matriculas
from disciplina d
join matricula m on d.id = m.disciplina_id
group by d.departamento
order by total_matriculas;
```
