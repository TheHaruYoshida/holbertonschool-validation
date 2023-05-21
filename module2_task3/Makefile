lint: ## Fail when the linter catches an error
	@golangci-lint run

build: lint ## Build the website
	@hugo
	@go build -o awesome-api

clean: stop ## Clean the dist folder
	@rm -rf dist/
	@rm -f awesome-api awesome.log
	@rm -f coverage-units.out coverage-integrations.out

post: ## Create a new blog post
	@hugo new posts/$(POST_NAME).md
	@echo "---\
	title: '$(POST_TITLE)'\
	date: $(date +"%Y-%m-%dT%H:%M:%S%z")\
	---" > content/posts/$(POST_NAME).md

help: ## Display the help command list
	@sed -ne '/@sed/!s/## //p' ${MAKEFILE_LIST}

run: ## Runs the application in background
	@./awesome-api >./awesome-api.log 2>&1 &

stop: ## Stops the application
	@pkill awesome-api

test: unit-tests integration-tests ## Test on certain space
	@echo "Test"

unit-tests: ## Execute the unit tests
	@go test -v -short -coverprofile=coverage-units.out

integration-tests: ## Execute the integration tests
	@go test -v -coverprofile=coverage-integrations.out