# Banco de Dados
Um banco de dados é uma coleção organizada de informações - ou dados - estruturadas, normalmente armazenadas eletronicamente em um sistema de computador. 

São divididos entre Relacional e Não-Relacional
- Relacional
Relaciona seus dados com outros dados de outras tabelas. Ex. Tabela de um paciente com seus tados, outa com o do medico, outra com o prontuario.
- Não-Relacinal
Um banco de dados não relacional é um banco de dados que não usa o esquema de tabela de linhas e colunas encontrado na maioria dos sistemas .

MongoDB é um banco de dados não relacional (noSQL) orientado a documentos no formato JSON.


![1-lwnlfl1ryn](https://user-images.githubusercontent.com/63822305/127707640-18f61f5e-4f21-4018-b9a7-cbb8ec4b0928.png)


### Acessando o mongo pela maquina 'Windows '

- [x] Ir em Propriedades do sistema.
- [x] Variáveis ​​de Ambiente e dependência do caminho da pasta onde esta instalado o mongo C: \ Program Files \ MongoDB \ Server \ 5.0 e de um ok.
- [x] Abra o prompt e passe a rota  cd C:\Program Files\MongoDB\Server\5.0\bin  enter 
- [x] mongod e pressionar enter.

### Demandas de Negocio

- Inserção de documentos
-  Atualização de documentos
- Exclusão de documentos
- Consulta com projeção
-  Consulta utilizando combinação entre os seletores
-  Consulta paginada e ordenada (utilizar skip, limit e sort)


#### Buscar o livro
```db.getCollection('json').find({})```

#### Deletar um livro
``` db.getCollection('livros').remove({ "categoria": { $ne: "psicologia" } })```

#### Inserindo um livro
```  db.livros.insertMany ```

####  Consulta combinando informações entre setores -  Espirita com mais de 150 paginas
```db.getCollection('livros').find({'categoria':'Espirita ' ,'pagina':{$gt:150}}) ```

####  Consulta ordenada com (skip, limit e sort) - Livro Espirita com a terceira menor quantidade de páginas
``` db.getCollection('livros').find({'categoria' :'Espirita'}).sort({pagina: 1}).skip(2).limit(1)```

####  Consulta com projeção - Livro Espirita ordenados do maior para o menor número de páginas
``` db.getCollection('livros').find({'categoria' : 'Espirita'}).sort({pagina : 1})```
