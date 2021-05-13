<img src="https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/back.png" width="300"/>
Esse repositório tem como objetivo demonstrar uma prática utilizando o banco de dados NoSQL MongoDB, que é um banco de dados de código aberto, gratuito, de alta performance, sem esquemas e orientado à documentos JSON (armazenados em modo binário, apelidado de JSON), muitas aplicações podem modelar informações de modo muito mais natural, pois os dados podem ser aninhados em hierarquias complexas e ainda serem indexáveis e fáceis de buscar.<br>
* Prática realizada em docker.

### ✍️ 1- Criar o banco de dados com seu nome.
  * Para resolução dessa questão, será necessária algunas etapas:
  1- Para isso é necessário primeiramente iniciar o mongodb através do docker-compose sob o comando: `docker-compose up -d`.
 ![imagem1](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem1.png)
  2- Para acesso ao terminal do mongodb, usamos o comando: `docker exec -it mongo bash` e depois o `mongo`
 ![imagem2](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem2.png)
 * O mongo Express `http://localhost:8081/`- é a interface gráfica de acesso ao mongo do docker
 ![localhost](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/localhost.jpg)
  3- Nessa etapa já odemos atender a questão, para isso podemos criar o banco de dados com o comando `use nomedobanco`
 ![imagem3](https://github.com/vandisney/NoSQL-MongoDB/blob/main/imagens/imagem3.png)

Exercício – Comandos Básicos


2. Listar os banco de dados
3. Criar a collection produto no bd com seu nome
4. Listar os banco de dados
5. Listar as collections
6. Inserir os seguintes documentos na collection produto:
• _id: 1, "nome": “cpu i5", "qtd": "15“
• _id: 2, nome: “memória ram", qtd: 10, descricao: {armazenamento: “8GB”, tipo:“DDR4“}
• _id: 3, nome: "mouse", qtd: 50, descricao: {conexao: “USB”, so: [“Windows”, “Mac”, “Linux“]}
• _id: 4, nome: “hd externo", "qtd": 20, descricao: {conexao: “USB”, armazenamento: “500GB”, so:
[“Windows 10”, “Windows 8”, “Windows 7”]}

7. Mostrar todos os documentos
