## Prerequisites

go Hugo 0.80+
gnu Make 4+
Mozilla or Chrome or Edge navigator


## Lifecycle

it has 3 stages:
### build step:
	creates website and locates it in the dist/ directory
### clean step:
	cleans dist directory
### post step:
	acepts 2 parameters POST_NAME and POST_TITLE, the first one
	gives the name of the post(without extension .md) and the
	second one gives the title of the post. After this the post
	will be created with command 'make POST_NAME POST_TITLE post'

### validate:
	 should validate the file ./dist/index.html by using the command line Holberton's W3C Validator, but should not fail if the file is not valid: you expect it to be a n	       on-blocking quality indicator. ' /home/carlos/W3C-Validator/w3c_validator.py ./dist/index.html'

### check:
	 should fail when one of the 2 following steps fails:Lint of the Markdown source files using the command line "markdownlint-cli" Analysis of the links with the
	 command line "markdown-link-check"     markdownlint /content/posts/*  &&  markdown-link-check ./content/posts/* && echo 'SUCCESS' || echo 'FAIL' || echo 'FAIL'
         markdownlint ./content/posts/* && markdown-link-check ./content/posts/* && echo 'SUCCESS' || echo 'FAIL'

### help:
	command make help will gives a description of every command.

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
	 
### Workflow
	iscover, create, and share actions to perform any job you'd like, including CI/CD, and combine actions in a completely customized workflow.
