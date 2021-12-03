build: ## construlle una pagina estatica con hugo y la guarda en dist 
	hugo -D > /dev/null 2>&1

.PHONY: clean
clean: ## elimina el directorio dist dentro de module1...
	rm -rf ./dist/ > /dev/null 2>&1

post: ## crea un nuevo post en la carpeta que esta configurada en config.toml acepta dos argumentos el nombre del archivo .md (POST_NAME sin la extension) y el titulo del post (POST_TITLE)
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2010-03=26T08:47:11+01:00\ndraft: false\n---' > ./content/posts/$(POST_NAME).md  	
check: ## should fail when one of the 2 following steps fails:Lint of the Markdown source files using the command line "markdownlint-cli" Analysis of the links with the command line "markdown-link-check"	markdownlint /content/posts/*  &&  markdown-link-check ./content/posts/* && echo 'SUCCESS' || echo 'FAIL' || echo 'FAIl'
	markdownlint ./content/posts/welcome.md >/dev/null 2>&1 &&  markdown-link-check -q ./content/posts/welcome.md >/dev/null 2>&1
          
			


validate: ## should validate the file ./dist/index.html by using the command line Holberton's W3C Validator, but should not fail if the file is not valid: you expect it to be a non-blocking quality indicator.
	/home/carlos/W3C-Validator/w3c_validator.py ./dist/index.html > /dev/null 2>&1 || true;
	     
help: ## da una breve descripcion de todos los comandos
	grep '##' ./Makefile  | sed 's/ ##/ /' |  head -n -1



