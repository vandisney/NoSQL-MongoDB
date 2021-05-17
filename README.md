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
   > db.produto.insertOne({_id: 2, nome: "memória ram", qtd: 10, descricao: {armazenamento: "8GB", tipo:"DDR4"}})</br>
   > db.produto.insertOne({_id: 3, nome: "mouse", qtd: 50, descricao: {conexao: "USB", so: ["Windows", "Mac", "Linux"]}})</br>
   > db.produto.insertOne({_id: 4, nome: "hd externo", "qtd": 20, descricao: {conexao: "USB", armazenamento: "500GB", </br>
  so: ["Windows 10", "Windows 8", "Windows 7"]}})</br>
  </p>

![imagem7](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem7.png)

### ✍️ 5- Pesquisar na collection produto, os documentos com os seguintes atributos:
  * 5.1- Nome = mouse - Realizado através da consulta: `db.produto.find({nome: "mouse"})`
![imagem8](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem8.png)

* 5.2- Quantidade = 20 e apresentar apenas o campo nome -> Realizado através da consulta: `db.produto.find({qtd: 20},{_id: 0, nome: 1 })`
![imgem9](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imgem9.png)

* 5.3- Quantidade <= 20 e apresentar apenas os campos nome e qtd -> Realizado através da consulta: `db.produto.find({qtd: {$lte: 20}},{_id: 0, nome: 1,qtd: 1 })`
![imagem10](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem10.png)

* 5.4- Quantidade entre 10 e 20 -> Realizado através da consulta: `db.produto.find({qtd: {$gte: 10, $lte: 20}})`
> Para esse questão foi consultado primeiramente a qtd maior que 10 sob o comando: `db.produto.find({qtd: {$gte: 10}})` e, segundo a imagem foi observado o item: 3 retorna a qtd: 50, porém este item não foi retornado na consulta que atendeu a questão, validando a consulta.
![imagem11](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagm11.png)

### ✍️ 6- Conexão = USB e não apresentar o campo _id e qtd -> Realizado através da consulta: `db.produto.find({"descricao.conexao": "USB"},{_id: 0,qtd: 0})`
  * 5.1- Nome = mouse - Realizado através da consulta: `db.produto.find({nome: "mouse"})`
![imagem12](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem12.png)

### ✍️ 7- SO que contenha “Windows” ou “Windows 10” -> Realizado através da consulta: `db.produto.find({"descricao.so":{$in: ["Windows","Windows 10"]}})`
 ![imagem13](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem13.png)




