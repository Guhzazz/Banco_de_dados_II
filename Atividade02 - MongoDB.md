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

# Parte 3 - Consultas com Arrays

## Exercício 14
`db.conteudos.find({ genero: "Drama"})`

## Exercício 15
`db.conteudos.find({genero: "Ficção Científica"})`

## Exercício 16
`db.conteudos.find({$and:[{ genero: "Drama"}, { genero: "Ficção Científica"}]})`

## Exercício 17
`db.usuarios.find({interesses: "Suspense"})`

## Exercício 18
`db.conteudos.find($or[{genero: "Terror"}, {genero: "Mistério"}])`

## Exercício 19
`db.conteudo.find({genero: {$not: {"Comédia"}}})`

# Parte 4 - Objetos Aninhados

## Exercício 20
`db.conteudos.find({ "diretor.nome" : "Christopher Nolan" })`

## Exercício 21
`db.conteudos.find({ "diretor.pais" : "Reino Unido"})`

## Exercício 22
`db.usuarios.find({"endereco.bairro" : "Centro"})`

## Exercício 23
`db.usuarios.find({ endereco:{ $exists: true}})`

## Exercício 24
`db.usuarios.find({ endereco:{ $exists: false}})`

# Atualizações Básicas
## Exercício 25
`db.usuarios.updateOne(
  { nome: "Carlos Lima" },
  { $set: { ativo: true } }
)`

## Exercício 26
`db.conteudos.updateOne(
  { titulo: "Cidade de Deus" },
  { $set: { disponivel: true } }
)`

## Exercício 27
`db.conteudos.updateOne(
  { titulo: "Matrix" },
  { $set: { idiomaOriginal: "Inglês" } }
)`

## Exercício 28
`db.conteudos.updateOne(
  { titulo: "Interestelar" },
  { $set: { classificacao: "10+" } }
)`

## Exercício 29 
`db.conteudos.updateOne(
  { titulo: "Avatar" },
  { $set: { avaliacaoMedia: 9.0 } }
)`
