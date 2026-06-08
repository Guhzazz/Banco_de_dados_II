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

