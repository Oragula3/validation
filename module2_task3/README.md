## Prerequisites

	You should have a basic knowledge on the following concepts:

	What a compiled language is (C/C#/Golang/Rust/etc.)

	Generation process from source to executable binary
	Basic types: string, integer, boolean, maps, arrays
	Basic algorithmic: loops, conditional, functions
	Installing command line tools with NPM (in addition to package managers)

	Understand the basics of the HTTP protocol (client/server, verbs, headers)

	Tooling
	This project needs the following tools / services:

	Same tools as previous module
	Golang in v1.15.*
	NPM v7+ with NodeJS v14.* (stable)
	Python 3 with pip module

## Lifecycle

	It has 3 stages:
### help:
	command make help will gives a description of every command.

### build step:
	 compile the source code of the application to a binary named awesome-api
	 (the name awesome-api comes from the command go mod init 
	 github.com/<your github handle>/awesome-api) with the command go build.	

### lint step:
	 to execute a static analysis to lint this code.

### run step:
	 Run the application in background by executing the binary awesome-api, 
	 and write logs into a file named awesome.log with the command ./awesome-api
	 >./awesome.log 2>&1 &.

### clean step:
	cleans dist directory

### stop step:
	Stop the application with the command kill XXXXX where XXXXX is the Process
	 ID of the application. For instance: kill "$(pgrep awesome-api)".

### Test step:
	You want to test it to ensure that it behaves as expected. With the application
	started, you may want to use the command line curl (or your web browser, or the
	command wget or any other HTTP client):

### unit-tests step:
	executes the Golang unit tests

### integration-tests step:
	 to validate that the functions are behaving as expected when wired together.


