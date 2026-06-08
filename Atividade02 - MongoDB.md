# Parte 1 - Primeiros Contatos
## Exerício 1
`db.usuarios.find()`

## Exercício 2
`db.conteudos.find()`

## Exercício 3
`db.usuarios.find({cidade: "Curitiba"})`

## Exercício 4
`db.conteudos.find({tipo: "filme"})`

## Exercício 5
`db.conteudos.find({titulo: "Matrix"})`

## Exercício 6
`db.usuarios.insertOne({
    nome: "gustavo",
    email: "ra139067",
    idade: 19,
    cidade: "Maringá",
    estado: "Paraná",
    interesses: ["Estudar", "Jogar Video Games"],
    ativo: true
})`

## Exercício 7
`db.conteudos.insertOne({
  titulo: "De Volta para o Futuro",
  tipo: "filme",
  ano: 1985,
  generos: ["Ficção Científica", "Aventura", "Comédia"],
  avaliacaoMedia: 8.5,
  duracaoMinutos: 116,
  disponivel: true
})`

# Parte 2 - Operadores de Comparação

## Exercício 8
`db.conteudos.find({ avaliacaoMedia: { $gt: 9 } })`

## Exercício 9
`db.usuarios.find({idade: { $gt: 30 } })`

## Exercício 10
`db.conteudos.find({ ano: { $lt: 2010 } })`

## Exercício 11
`db.conteudos.find({ano: { $gte: 2015} })`

## Exercício 12
`db.conteudos.find({avaliacaoMedia: { $lte: 8.8 }})`

## Exercício 13
`db.usuarios.find({ estado: { $ne: "PR" } })`
