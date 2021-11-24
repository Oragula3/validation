lint: ## to execute a static analysis to lint this code.
	golangci-lint run

build: ## compiles the awesome-api application
	make lint
	go build

run: ## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome.log with the command ./awesome-api >./awesome.log 2>&1 &.
	./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application. For instance: kill "$(pgrep awesome-api)".
	kill $$(pgrep -f "awesome-api")

.PHONY : clean
clean: ## Delete the binary awesome-api and the log file awesome-api.log it also removes de coverage profiles
	make stop > /dev/null 2>&1 &
	rm -rf ./awesome-api ./awesome.log ./coverage-units.out ./coverage-integrations.out> /dev/null 2>&1

unit-tests: ## executes (successfully) the Golang unit tests
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## executes the golang integration tests
	go test -v -tags=integration -coverprofile=coverage-integrations.out

test: ## test the app with command curl http://localhost:9999 sending the message "404 Page Not Found" and curl http://localhost:9999/health sending the message "ALIVE"
	make unit-tests && make integration-tests

help: ## gives a descriptios of every command
	grep '##' ./Makefile  | sed 's/ ##/ /' |  head -n -1
