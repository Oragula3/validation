lint: ## to execute a static analysis to lint this code.
	golangci-lint run
	
build: ## construlle una pagina estatica con hugo y la guarda en dist y compiles the awesome-api application
	hugo -D > /dev/null 2>&1
	make lint
	go build

run: ## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome.log with the command ./awesome-api >./awesome.log 2>&1 &.
	./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application. For instance: kill "$(pgrep awesome-api)".
	kill $$(pgrep -f "awesome-api")

.PHONY: clean
clean: ## elimina el directorio dist dentro de module1...
	rm -rf ./dist/ > /dev/null 2>&1
	make stop > /dev/null 2>&1 &
	rm -rf ./awesome-api ./awesome.log ./coverage-units.out ./coverage-integrations.out> /dev/null 2>&1
	
unit-tests: ## executes (successfully) the Golang unit tests
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## executes the golang integration tests
	go test -v -tags=integration -coverprofile=coverage-integrations.out

test: ## test the app with command curl http://localhost:9999 sending the message "404 Page Not Found" and curl http://localhost:9999/health sending the message "ALIVE"
	make unit-tests && make integration-tests

post: ## crea un nuevo post en la carpeta que esta configurada en config.toml acepta dos argumentos el nombre del archivo .md (POST_NAME sin la extension) y el titulo del post (POST_TITLE)
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2010-03=26T08:47:11+01:00\ndraft: false\n---' > ./content/posts/$(POST_NAME).md
		
check: ## should fail when one of the 2 following steps fails:Lint of the Markdown source files using the command line "markdownlint-cli" Analysis of the links with the command line "markdown-link-check"	markdownlint /content/posts/*  &&  markdown-link-check ./content/posts/* && echo 'SUCCESS' || echo 'FAIL' || echo 'FAIl'
	markdownlint ./content/posts/welcome.md >/dev/null 2>&1 &&  markdown-link-check -q ./content/posts/welcome.md >/dev/null 2>&1

validate: ## should validate the file ./dist/index.html by using the command line Holberton's W3C Validator, but should not fail if the file is not valid: you expect it to be a non-blocking quality indicator.
	/home/john/Desktop/Curso_DevOps/W3C-Validator/w3c_validator.py ./dist/index.html > /dev/null 2>&1 || true;
	     
help: ## da una breve descripcion de todos los comandos
	grep '##' ./Makefile  | sed 's/ ##/ /' |  head -n -1

package: ## para generar el ZIP
	zip -r awesome-website.zip Makefile dist/*

