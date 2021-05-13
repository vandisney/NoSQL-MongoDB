<img src="https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/back.png" width="300"/>
Esse repositório tem como objetivo demonstrar uma prática utilizando o banco de dados NoSQL MongoDB, que é um banco de dados de código aberto, gratuito, de alta performance, sem esquemas e orientado à documentos JSON (armazenados em modo binário, apelidado de JSON), muitas aplicações podem modelar informações de modo muito mais natural, pois os dados podem ser aninhados em hierarquias complexas e ainda serem indexáveis e fáceis de buscar.<br>
* Prática realizada em docker.

### ✍️ 1- Criar o banco de dados com seu nome.
  * Para resolução dessa questão, será necessária algunas etapas: </br>
  1- Para isso é necessário primeiramente iniciar o mongodb através do docker-compose sob o comando: `docker-compose up -d`.
 ![imagem1](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem1.png)
  2- Para acesso ao terminal do mongodb, usamos o comando: `docker exec -it mongo bash` e depois o `mongo`.
 ![imagem2](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem2.png)
 * O mongo Express `http://localhost:8081/`- é a interface gráfica de acesso ao mongo do docker.
 ![localhost](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/localhost.jpg)
  3- Nessa etapa já podemos atender a questão, para isso podemos criar o banco de dados com o comando: `use nomedobanco`.
 ![imagem3](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem3.png)
 
 ### ✍️ 2- Listar os banco de dados e criar a collection produto no bd com seu nome.
  Com o comando: `show dbs` é possível listar os bancos de dados existentes. Conforme a imagem nota-se que o banco de dados criado na questão anterior não foi exibido, para visualizar o banco de dados é necessário incluir um collections - seria uma tabela comparando-se ao banco relacional.
 ![imagem4](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem4.png)
* Criação da collections com o comando: `db.createCollection('produto')`
![imagem5](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem5.png)

### ✍️ 3- Listar as collections.
  Para isso damos um `show collections`
  ![imagem6](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem6.png)

### ✍️ 4- Inserir os seguintes documentos na collection produto.
  <p>
  _id: 1, "nome": “cpu i5", "qtd": "15“ </br>
  _id: 2, nome: “memória ram", qtd: 10, descricao: {armazenamento: “8GB”, tipo:“DDR4“}</br>
  _id: 3, nome: "mouse", qtd: 50, descricao: {conexao: “USB”, so: [“Windows”, “Mac”, “Linux“]}</br>
  _id: 4, nome: “hd externo", "qtd": 20, descricao: {conexao: “USB”, armazenamento: “500GB”, so:[“Windows 10”, “Windows 8”, “Windows 7”]}</br>
  </p>
* A inserção foi possível através do comando abaixo:
  <p>
   > db.produto.insertOne({_id: 1, "nome": "cpu i5", "qtd": "15"})</br>
  { "acknowledged" : true, "insertedId" : 1 }</br>
  > db.produto.insertOne({_id: 2, nome: "memória ram", qtd: 10, descricao: {armazenamento: "8GB", tipo:"DDR4"}})</br>
  { "acknowledged" : true, "insertedId" : 2 }</br>
  > db.produto.insertOne({_id: 3, nome: "mouse", qtd: 50, descricao: {conexao: "USB", so: ["Windows", "Mac", "Linux"]}})</br>
  { "acknowledged" : true, "insertedId" : 3 }</br>
  > db.produto.insertOne({_id: 4, nome: "hd externo", "qtd": 20, descricao: {conexao: "USB", armazenamento: "500GB", </br>
  so: ["Windows 10", "Windows 8", "Windows 7"]}})</br>
  { "acknowledged" : true, "insertedId" : 4 }</br>
  </p>

![imagem7](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem7.png)
