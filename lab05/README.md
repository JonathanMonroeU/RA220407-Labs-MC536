# Aluno
* `220407`: `Lindon Jonathan Sanley dos Santos Pereira Monroe`

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução
~~~cypher
MATCH (m:Marcador)-[:Pertence]->(c:Categoria {id: 'Serviços'})
RETURN m
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução
~~~cypher
MATCH (m:Marcador)-[:Pertence]->()-[:Superior*0..]->(c:Categoria {id:"Serviços"})
RETURN m
~~~
