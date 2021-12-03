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

