#Como instalar o NodeJS, Bower e Gulp no servidor compartilhado#

##Instalando NodeJS##

- Navegar até a pasta do projeto utilizando o terminal ssh
- Executar o comando: 
	```
	$ wget https://nodejs.org/dist/v4.4.2/node-v4.4.2-linux-x64.tar.gz --no-check-certificate
	```

- Após finalizar o download, executar o comando para extrair o conteúdo: 
	```
	$ tar xvf node-v4.4.2-linux-x64.tar.gz
	```	

- Após finalizar a extração do pacote, executar o comando para renomear a pasta: 
	```
	$ mv node-v4.4.2-linux-x64 node
	```

- Feito isso, o arquivo node-v4.4.2-linux-x64.tar.gz não é mais necessário e pode ser excluído com o comando: 
	```
	$ rm node-v4.4.2-linux-x64.tar.gz
	```

##Instalando o bower##

- Ainda na pasta do projeto, executar o comando: 
	```
	$ node/bin/npm install bower
	```

- Criar link simbólico com o comando: 
	```
	$ ln -s node_modules/bower/lib/bin/bower.js bower
	```
- Editar o caminho do NodeJS no bower para que ele funcione localmente:
	- Entre na pasta node/bin e execute o comando ***$ pwd*** para exibir seu caminho completo. Copie este caminho. Volte para a pasta do projeto ao finalizar este passo  
	
	- Abra o arquivo do Bower no editor de texto nano com o comando: 
	```
	$ nano node_modules/bower/bin/bower
	```

	- Edite a primeira linha e substitua pelo caminho completo do NodeJS copiado anteriormente. Salve com *Ctrl + O* e feche com  *Ctrl + X*

- Para instalar os componentes com o bower basta executar o comando: 
	```
	$ ./bower install "componente"
	```

- Exemplo:
	```
	$ ./bower install angular
	```

##Instalando o Gulp##

- Ainda na pasta do projeto, executar o comando: 
	```
	$ node/bin/npm install gulp
	```

- Criar link simbólico com o comando: 
	```
	$ ln -s node_modules/gulp/bin/gulp.js gulp
	```

- Para executar as tarefas do gulpfile.js basta executar o comando: 
	```
	$ ./gulp
	```
