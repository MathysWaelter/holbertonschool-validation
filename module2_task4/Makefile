help: ## Show help command
	@sed -ne '/@sed/!s/## //p' Makefile

build:  ## Create Website
	@hugo

clean:  ## Delete content of dist folder
	@rm -rf dist/*

post:  ## Create a post
	@hugo new ./content/posts/$(POST_NAME).md
	@sed -i '/title:*/c\title: "$(POST_TITLE)"' ./content/posts/$(POST_NAME).md

check: ## check with markdown
	@markdownlint *
	@markdown-link-check *

validate: ## validate with W3C
	@./w3c_validator.py ./dist/index.html