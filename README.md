# Instala��o do Projeto e Anota��es importantes

* Criar pasta do projeto
* dentro da pasta, rodar o comando: **npm init -y**
* instalar o framework express com o comando: **npm install express**
* criar arquivo **index.js** na raiz do projeto
* para come�ar a desenvolver, vamos importar o express para dentro do arquivo: ex: **const express = require(?express?);**
* criar uma vari�vel que vai armazenar a aplica��o, instanciando a express ex: **const app = express();**
* agora precisamos mandar a aplica��o ouvir a porta **3333 ex: app.listen(3333);**
* para ver o resultado no navegador, rode o comando: node index.js e depois acesse o **localhost:3333**
* Para facilitar o processo de desenvolvimento, � interessante instalar o nodemon para que n�o seja necess�rio reiniciar o servidor toda vez que fizer alguma altera��o no arquivo raiz da aplica��o, para isso, na pasta do projeto rode o comando: **npm install nodemon -D**
* feito isso, � necess�rio o arquivo **package.json** que estar� na raiz do projeto, alterar  a linha que estar� escrito: **"test": "echo \"Error: no test specified\" && exit 1"** por **"start": "nodemon index.js"** ou simplesmente adicionar esta linha nova abaixo do comando j� existente 
* feito isso � s� rodar o comando npm start e toda altera��o que for feita, ser� carregada automaticamente rodando o comando **npm start**

# Conectando ao Banco de Dados (SQlite)
* Para conectar com o banco de dados, primeiro � necess�rio instalar a biblioteca **knexjs**, dispon�vel em http://knexjs.org/, siga o passo-a-passo de instala��o dentro da raiz do projeto
* ap�s a instala��o, se for fazer o uso do sqlite crie uma pasta dentro do **src** ou **raiz** do projeto chamada **database**, onde ficar� armazenado o arquivo de configura��o do banco de dados
* feito isso, v� ao arquivo **knexfile.js**, localize a linha onde fica o **development** e coloque o caminho do arquivo que voc� criar� para configurar a base, ex:
**filename: ?./src/database/db.sqlite?**
* dentro da pasta database crie uma pasta chamada migrations
* dentro do aquivo **knexfile.js**, adicione a localiza��o da sua pasta **migrations**
* abaixo do objeto **migrations**, adicione a linha **useNullAsDefault: true,**
* ap�s isso, para criar as tabelas dentro do sqlite, rode o seguinte comando:  **npx knex migrate:make create_nomedatabela**
ao rodar o comando acima, note que ele criar� um arquivo dentro de onde vc pr�-determinou 
* feito isso, deve-se rodar o comando: **npx knex migrate:latest**
e ent�o a tabela ser� criada
