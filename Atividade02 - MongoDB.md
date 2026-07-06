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
`db.conteudo.find({genero: {$ne: {"Comédia"}}})`

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

# Parte 5 - Atualizações Básicas
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

# Parte 6 - Atualizações com operadores
## Exercício 30
`db.conteudos.updateOne(
    {titulo: "Matrix"},
    {$inc :{ visualizacoes: 1} }
)` 

## Exercício 31
`db.conteudos.updateMany(
    {},
    {$inc :{visualizacoes: 1000} }
)`    

## Exercício 32
`db.conteudos.updateOne(
    {titulo: "Matrix"},
    {$push :{genero: "Clássico"} }
)`    

## Exercício 33
`db.conteudos.updateOne(
    {titulo: "Matrix"},
    {$pull :{genero: "Clássico"} }
)`    

## Exercício 34
`db.usuarios.updateOne(
    {nome: "Beatriz Nunes"},
    {$unset :{telefone: ""} }
)`   

## Exercício 35
`db.assinaturas.updateMany(
    {plano: "Premium"},
    {$push :{beneficios: "sem anúncios"} }
)`

# Parte 7 - Operadores lógicos
## Exercício 36
`db.conteudos.find({
  $and: [
    { tipo: "filme" },          
    { avaliacaoMedia: { $gt: 9 } } 
  ]
});`

## Exercício 37
`db.usuarios.find({
  $or: [
    { cidade: "Curitiba" },          
    {cidade: "Maringá"" } 
  ]
});`

## Exercício 38
`db.conteudos.find({
  $or: [
    {tipo: "série" },          
    {tipo: "documentário" } 
  ]
});`

## Exercício 39
`db.conteudos.find({
  $or: [
    {avaliacaoMedia: {$gt: 9} },          
    {visualizacoes: {$gt: 200000} } 
  ]
});`

## Exercício 40
`db.usuarios.find({
  $or: [
    {ativo: true },          
    {idade: {$lt: 30} } 
  ]
});`

# Parte 8 - Campos opcionais e flexibilidade NoSQL
## Exercício 41
`db.conteudos.find(
    {premios: { $exists: true }}
);`

## Exercício 42
`db.conteudos.find(
    {diretor: { $exists: false }}
);`

## Exercício 43
`db.usuarios.find(
    {premium: { $exists: true }}
);`

## Exercício 44
`db.conteudos.find(
    {temporadas: { $exists: true }}
);`

## Exercício 45
`Isso ocorre pela característica do NoSQL de não ter tabelas com campos fixos. Isso permite criação dinâmica de valores, não sendo necessário de ater a estruturas rígidas, como ocorre em bancos relacionais. Na coleção conteudos, isso é ainda mais fundamental, visto que essa coleção pode ter itens do tipo filme, série que possuirão campos extras diferentes, como número de episódios, no caso das séries, e duração, no caso dos filmes.
`
# Parte 9 - Remoção de documentos
## Exercício 46
`db.usuarios.deleteOne(
    {email: "ra139067"}
);`

## Exercício 47
`db.conteudos.deleteOne(
    {titulo: "De volta para o futuro"}
);`

## Exercício 48
`db.avaliacoes.deleteOne(
    {nota: {$lt: 8}}
);`

## Exercício 49
`db.historico.deleteOne(
    {progressoPercentual: {$lt: 40}}
);`

## Exercício 50
 Ao guardar tudo em um documento, a eficiência de leitura cresceria, mas os documentos ficariam gigantes e haveria duplicação de dados. Ao separar em coleções, é mais fácil atualizar visto que é só mudar um documento ao invés de alterar muitas referências.


## Exercício 51
 Ao se aninhar informações dentro dos documentos, a vantagem é que não é necessário cruzar coleções para se ter oq precisa na consulta. Porém, isso aumenta o tamanho dos documentos e pode haver um estouro se os dados dentro do documento crescer indefinidamente.

## Exercício 52
A referência entre coleções deve ser usada quando os dados crescem indefinidamente (como históricos e avaliações), evitando estourar o limite de 16 MB por documento. Ela também é ideal quando a informação é compartilhada por vários registros, o que evita duplicar dados e facilita atualizações, ou quando as informações precisam de consultas e relatórios independentes.

## Exercício 53
Dados incorporados são ideais quando as informações são intimamente ligadas e lidas quase sempre juntas, como um endereço dentro do perfil do usuário. Também devem ser usados quando os dados secundários possuem um tamanho controlado e previsível, garantindo que o documento nunca passe do limite de 16 MB, ou quando você precisa da máxima velocidade de leitura, recuperando tudo em uma única busca no disco.
