# Instalação do Projeto e Anotações importantes

* Criar pasta do projeto
* dentro da pasta, rodar o comando: **npm init -y**
* instalar o framework express com o comando: **npm install express**
* criar arquivo **index.js** na raiz do projeto
* para começar a desenvolver, vamos importar o express para dentro do arquivo: ex: **const express = require(?express?);**
* criar uma variável que vai armazenar a aplicação, instanciando a express ex: **const app = express();**
* agora precisamos mandar a aplicação ouvir a porta **3333 ex: app.listen(3333);**
* para ver o resultado no navegador, rode o comando: node index.js e depois acesse o **localhost:3333**
* Para facilitar o processo de desenvolvimento, é interessante instalar o nodemon para que não seja necessário reiniciar o servidor toda vez que fizer alguma alteração no arquivo raiz da aplicação, para isso, na pasta do projeto rode o comando: **npm install nodemon -D**
* feito isso, é necessário o arquivo **package.json** que estará na raiz do projeto, alterar  a linha que estará escrito: **"test": "echo \"Error: no test specified\" && exit 1"** por **"start": "nodemon index.js"** ou simplesmente adicionar esta linha nova abaixo do comando já existente 
* feito isso é só rodar o comando npm start e toda alteração que for feita, será carregada automaticamente rodando o comando **npm start**

# Conectando ao Banco de Dados (SQlite)
* Para conectar com o banco de dados, primeiro é necessário instalar a biblioteca **knexjs**, disponível em http://knexjs.org/, siga o passo-a-passo de instalação dentro da raiz do projeto
* após a instalação, se for fazer o uso do sqlite crie uma pasta dentro do **src** ou **raiz** do projeto chamada **database**, onde ficará armazenado o arquivo de configuração do banco de dados
* feito isso, vá ao arquivo **knexfile.js**, localize a linha onde fica o **development** e coloque o caminho do arquivo que você criará para configurar a base, ex:
**filename: ?./src/database/db.sqlite?**
* dentro da pasta database crie uma pasta chamada migrations
* dentro do aquivo **knexfile.js**, adicione a localização da sua pasta **migrations**
* abaixo do objeto **migrations**, adicione a linha **useNullAsDefault: true,**
* após isso, para criar as tabelas dentro do sqlite, rode o seguinte comando:  **npx knex migrate:make create_nomedatabela**
ao rodar o comando acima, note que ele criará um arquivo dentro de onde vc pré-determinou 
* feito isso, deve-se rodar o comando: **npx knex migrate:latest**
e então a tabela será criada
