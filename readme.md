<div style="text-align:center">  
<img src ="./images/minas.png">
<img src="./images/reprograma-fundos-claros.png" width="40%" height="40%">   <img src="./images/pessoas.png" width="30%" height="30%">

# **Reprograma + Porto Digital - Mulheres em Inovação, Negócios e  Artes (MINAs)** 

# reprogramaSemana12
### *Assunto da semana: Banco de dados*

## <blockquote> "não lembre do código, lembre de como você resolve o problema" </blockquote>
</div>

## atividadeSemana12 :books: :green_book:

### :memo: Briefing
<div style="text-align:justify">
No último domingo nos foram apresentados conceitos relativo ao assunto banco de dados, no entanto, devido a alguns impresvistos, a atividade da semana não se constituirá no desenvolvimento de um sistema integrado a um banco de dados, mas em um resumo sobre o que foi visto.
</div>

<div style="text-align:center">
siglas utilizadas no texto:

**BD** --> Banco de dados

![](/images/db.gif)

### 1. CONCEITO DE BANCO DE DADOS

</div>
<div style="text-align:justify">
<blockquote> Um banco de dados é um local no qual são armazenados uma série de informações com alguma finalidade, as quais representam algo do mundo real e são organizadas em **entidades** que têm **atributos**. Podem ser utilizados em diversos contextos, desde o armazenamento e gerenciamento de dados de um site até como forma de controle de informações do RH de uma empresa. </blockquote>

Como entidades ligadas à área de *back-end*, apesar de existirem e serem acessados/atualizados cotidianamente, não é comum que pessoas que transitam na internet, se deem conta que eles existem.

Mas pode ter certeza que eles estão lá, servindo como uma  **"matéria-prima"** que é moldada pela lógica desenvolvida pelas *desenvolvedoras back-end* (que filtram quais dados serão exibidos ou não, quais dados serão exibidos somente em um acesso com login, etc) e são estruturados de maneira navegável pela *equipe de front-end* (responsável pela tradução dos dados filtrados em interfaces vistas pelos usuários).
</div>

<div style="text-align:center">

![](/images/db2.png)

### 2. BANCOS DE DADOS RELACIONAIS E NÃO RELACIONAIS

</div>

<div style="text-align:justify">
Os bancos de dados podem ser divididos em duas categorias: *relacional* e *não relacional*, sendo o *relacional* também chamado de Banco de Dados SQL (“Structured Query Language”) e o *não relacional* chamado de Banco de Dados NoSQL ("Not Only SQL").
</div>
<div style="text-align:center">

![](/images/SQL.png)

### RELACIONAIS
</div>
<div style="text-align:justify">
Em tradução livre, “Structured Query Language” quer dizer "Linguagem de Consulta Estruturada". 

Resumidamente, essa expressão fala sobre a característica dos BD relacionais de ser definido a partir de uma **linguagem de consulta**. Isso significa que antes de adicionar informações ao BD relacional é necessário desenvolver um modelo no qual entidades e atributos que serão armazenados são listados.

Visualmente, os banco de dados relacionais se parecem com tabelas de dados. 

Estruturalmente são rígidos, pois só é possível adicionar e manipular dados através de estruturas da de informações pré-definidas.
</div>
<div style="text-align:center">


![](/images/noSQL.png)

### NÃO-RELACIONAIS
</div>
<div style="text-align:justify">

Já os BD NoSQL são estruturas de dados mais dinâmicas as quais não apenas permitem o armazenamento em tabelas, mas também de forma orientada a documentos ou colunas, baseado em grafos ou organizado a partir de pares de "chave":"valor".

Tem como característica principal a flexibilidade, não necessitando de uma linguagem de consulta e modelos de arquiteturas de dados pré-definidos para armazenar informações.

No curso de *back-end* da **{reprograma}** estou aprendendo a utilizar uma ferramenta de Gerenciamento de Banco de Dados não-relacionais chamada **MONGO DB**. 

![](/images/mongodb.png)

*mas o que são sistemas de gerenciamento de bancos de dados*? 
</div>

<div style="text-align:center">

### SISTEMAS DE GERENCIAMENTO DE DADOS (SGBDs)

São softwares utilizados para auxiliar na gestão de estrutura de armazenamentos de dados, permitindo a manipulação de dados de maneira mais fácil e intuitiva.

</div>

<div style="text-align:center">

### COMANDOS APRENDIDOS

</div>

Abaixo, segue uma lista de comandos aprendidos e, abaixo de cada um, o retorno que aparece no terminal após sua execução.


0. **MONGOD**
```
mongod 
```
*Abre o mongo na nossa máquina*

1. **SHOW DATABASES** 
```
show databases 
```

![](/images/showDatabases.PNG)

*Mostra bancos de dados existentes e quanto da memória ocupam* 

2. **USE** 
```
use collectionAlunasReprograma 
```
![](/images/use.PNG)

*Cria uma coleção chamada collectionAlunasReprograma ou entra em uma já existente com esse mesmo nome*

3. **INSERT ONE**
``` 
db.collectionAlunasReprograma.insertoOne({"id": 1, "nome": "maré", "signo": "aquário"})
``` 
![](/images/insertOne.PNG)

*serve para adicionar um registro dentro de uma coleção que, no caso do exemplo, se constitui enquanto um objeto que representa uma entidade "aluna" e é composto pelos atributos id, nome e signo*.

``` 
db.collectionAlunasReprograma.insertMany([{"id": 2,"nome": "carla", "signo": "peixes"}, {"id": 3, "nome": "anna", "signo": "áries"} ]) 
``` 

![](/images/insertMany.PNG)

4. *insere um array de objetos (ou seja, uma série de entidades representadas por objetos) na collection ReprogramaAlunas*

```
show collections
``` 
![](/images/showCollections.PNG)

5. *Retorna as coleções existentes*

```
db.collectionAlunasReprograma.find() 
``` 
![](/images/find().PNG)

6. *É como listo as entidades que eu tenho em uma coleção*

``` 
db.collectionReprogramaAlunas.find().pretty()
```  
![](/images/findPretty.PNG)

7. *lista as coleções que tenho com uma formatação mais fácil de ler*



### FILTROS

Um filtro é um atributo que iremos utilizar como limitador do resultado da busca. No mongo, é possível fazer filtros dando atributos a serem filtrado no *find()*, por exemplo:

``` 
db.collectionAlunasReprograma.find({"signo":"aquário"}).pretty()
``` 
![](/images/findFiltro.PNG)

*traz os registros das alunas registradas como aquarianas*

Já unindo a função *find()* à *count()* é possível contar quantos elementos existem na categoria filtrada.

``` 
db.collectionReprograma.find({"turma":"aquário"}).count() 
``` 
![](/images/findCount.PNG)

*filtra e retorna o número de registros filtrados*
