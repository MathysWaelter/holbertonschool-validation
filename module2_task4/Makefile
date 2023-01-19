help: ## Show help command
	@sed -ne '/@sed/!s/## //p' Makefile

build:  ## Create Website
	@make validate >/dev/null 2>&1 && hugo || exit -1

clean:  ## Delete content of dist folder
	@rm -rf dist/*

post:  ## Create a post
	@hugo new ./content/posts/$(POST_NAME).md
	@sed -i '/title:*/c\title: "$(POST_TITLE)"' ./content/posts/$(POST_NAME).md

check: ## check with markdown
	@markdownlint content/posts/*
	@markdown-link-check content/posts/*

validate: ## validate with W3C
	@make build
	@./w3c_validator.py ./dist/index.html || true