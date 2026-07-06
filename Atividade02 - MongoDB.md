# Parte 1 - Primeiros Contatos
## Exerício 1
`db.usuarios.find()`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fe930ecb-cc91-4c8b-a02e-ff6bfbe89eba" />

## Exercício 2
`db.conteudos.find()`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/06926d28-ebcd-4e5a-8ca2-094aca89ee35" />

## Exercício 3
`db.usuarios.find({cidade: "Curitiba"})`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f4b8a54f-5417-4be9-8315-5f82bfe0f9c7" />

## Exercício 4
`db.conteudos.find({tipo: "filme"})`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ae48fddc-6c79-4c66-b0dc-440f009d84c0" />

## Exercício 5
`db.conteudos.find({titulo: "Matrix"})`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6be71f46-9c82-44c6-8aca-79da151faca9" />

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
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/56f28039-0098-419b-a0df-c2adee96c515" />

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
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1e018d24-9f6f-4dfa-ae93-dbbad1c54eb8" />

# Parte 2 - Operadores de Comparação

## Exercício 8
`db.conteudos.find({ avaliacaoMedia: { $gt: 9 } })`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/853a12ce-d458-476f-9dac-0908ce0a6ac2" />

## Exercício 9
`db.usuarios.find({idade: { $gt: 30 } })`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bfdcd2f2-46fc-4432-a9b1-23fe649d2273" />

## Exercício 10
`db.conteudos.find({ ano: { $lt: 2010 } })`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1a40af42-dacb-42ee-98bf-fb21f7b9514a" />

## Exercício 11
`db.conteudos.find({ano: { $gte: 2015} })`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/21b9f58c-c253-4ef2-bab2-e44db6ca3ca4" />

## Exercício 12
`db.conteudos.find({avaliacaoMedia: { $lte: 8.8 }})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/423a1af7-0088-4961-a33f-46be6a2977a6" />

## Exercício 13
`db.usuarios.find({ estado: { $ne: "PR" } })`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e4d91266-90d0-4ad5-aae6-bafe3095b746" />

# Parte 3 - Consultas com Arrays

## Exercício 14
`db.conteudos.find({ genero: "Drama"})`

## Exercício 15
`db.conteudos.find({genero: "Ficção Científica"})`

## Exercício 16
`db.conteudos.find({$and:[{ genero: "Drama"}, { genero: "Ficção Científica"}]})`

## Exercício 17
`db.usuarios.find({interesses: "Suspense"})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9443d319-278f-4e43-8ff3-17d3301ed80f" />

## Exercício 18
`db.conteudos.find($or[{genero: "Terror"}, {genero: "Mistério"}])`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/266bfd12-11c3-47e5-bb8d-f0be0e97e37f" />

## Exercício 19
`db.conteudo.find({genero: {$ne: {"Comédia"}}})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9336c0c7-6afd-445c-ac4c-561683d519dd" />

# Parte 4 - Objetos Aninhados

## Exercício 20
`db.conteudos.find({ "diretor.nome" : "Christopher Nolan" })`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eb80665d-393f-4597-8091-bd565245e7c6" />

## Exercício 21
`db.conteudos.find({ "diretor.pais" : "Reino Unido"})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b5e7d90e-b902-4a89-bdfc-47b9ba506deb" />

## Exercício 22
`db.usuarios.find({"endereco.bairro" : "Centro"})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e5f109c4-45ee-4cff-b395-9e0738f2a6c4" />

## Exercício 23
`db.usuarios.find({ endereco:{ $exists: true}})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/df39306d-3df8-4a08-8af1-a48d8068075d" />

## Exercício 24
`db.usuarios.find({ endereco:{ $exists: false}})`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/11eef759-c967-4f05-96c4-287dfbc688c3" />

# Parte 5 - Atualizações Básicas
## Exercício 25
`db.usuarios.updateOne(
  { nome: "Carlos Lima" },
  { $set: { ativo: true } }
)`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/47ecbdce-420c-42bb-a1c9-5056c2110d46" />

## Exercício 26
`db.conteudos.updateOne(
  { titulo: "Cidade de Deus" },
  { $set: { disponivel: true } }
)`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ad004fe9-a075-486e-91fc-b11523d56005" />

## Exercício 27
`db.conteudos.updateOne(
  { titulo: "Matrix" },
  { $set: { idiomaOriginal: "Inglês" } }
)`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/31d84fba-82ee-4bb3-bf18-477682fcbeb8" />

## Exercício 28
`db.conteudos.updateOne(
  { titulo: "Interestelar" },
  { $set: { classificacao: "10+" } }
)`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/62c9d1e7-8ec4-463d-b0ae-a6272b2d1daa" />


## Exercício 29 
`db.conteudos.updateOne(
  { titulo: "Avatar" },
  { $set: { avaliacaoMedia: 9.0 } }
)`

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4b973bbf-43ad-40bb-9051-39b683e14372" />

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

# Prints dos demais resultados obtidos nas consultas
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205604" src="https://github.com/user-attachments/assets/be5780eb-7dc0-46ed-94bb-43cadd837f84" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205717" src="https://github.com/user-attachments/assets/63f0b9b6-587b-4888-b960-019425f5beb3" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205705" src="https://github.com/user-attachments/assets/c4023adc-f37f-4039-81d3-41728d797a5b" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205700" src="https://github.com/user-attachments/assets/9c645e6d-cf3a-4f34-923e-8e9e67bb004f" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205637" src="https://github.com/user-attachments/assets/f001c068-360c-4f99-9296-cc4693e6723b" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205629" src="https://github.com/user-attachments/assets/d9156325-5ba2-46a6-a923-500813649749" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205944" src="https://github.com/user-attachments/assets/b69b60d5-866d-405e-b0e9-753e8a0b724c" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205937" src="https://github.com/user-attachments/assets/68553161-1351-4089-9c8a-92f4601ec165" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205920" src="https://github.com/user-attachments/assets/26c7aef8-0ea3-4535-85fb-5a29609a014d" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205913" src="https://github.com/user-attachments/assets/169b60d6-47e3-4fff-822d-fb95f135cc1c" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205842" src="https://github.com/user-attachments/assets/3795b9be-591e-4032-af8f-f57794d1fe8a" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205825" src="https://github.com/user-attachments/assets/6909918f-a707-4d64-895f-bad99ecf5760" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205733" src="https://github.com/user-attachments/assets/7015ccef-fcb7-4354-862e-2e237b7104d1" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205725" src="https://github.com/user-attachments/assets/7ed17254-56d6-45df-b30e-216db0e32a4a" />
<img width="1920" height="1200" alt="Captura de tela 2026-06-29 205620" src="https://github.com/user-attachments/assets/2b7a927f-f5c6-4893-aa2a-161b4748985f" />


