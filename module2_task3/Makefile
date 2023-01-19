lint: ## Check with golint
	@golangci-lint run
 
help: ## Show help command
	@sed -ne '/@sed/!s/## //p' Makefile

build:  ## Create Website
	@golangci-lint run
	@go build

run: ## Run the application
	@./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
	@pkill awesome-api || true

test: ## Test the application
	@make unit-tests
	@make integration-tests

clean:  ## Delete content of dist folder
	@pkill awesome-api || true
	@rm -rf ./awesome-api && rm -rf awesome.log
	@rm -rf coverage*

unit-tests: ## unit-test for application
	@go test -v -short -coverprofile=coverage-units.out

integration-tests: ## intergrations test for application
	@go test -v -tags=integration -coverprofile=coverage-integrations.out

## Default
.PHONY: build clean run stop test lint unit-tests