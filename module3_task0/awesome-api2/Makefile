build: ## compiles the awesome-api application
	go build

run: ## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome.log with the command ./awesome-api >./awesome.log 2>&1 &.
	./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application. For instance: kill "$(pgrep awesome-api)".
	kill $(pgrep ./awesome-api)

.PHONY : clean
clean: ## Delete the binary awesome-api and the log file awesome-api.log
	rm -r ./awesome-api ./awesome.log

test: ## test the app with command curl http://localhost:9999 sending the message "404 Page Not Found" and curl http://localhost:9999/health sending the message "ALIVE"
	curl http://localhost:9999  
	curl http://localhost:9999/health 
	if [1 == 1];then echo "HIT: healthcheck/n"; fi	
help: ## gives a descriptios of every command
	grep '##' ./Makefile  | sed 's/ ##/ /' |  head -n -1

