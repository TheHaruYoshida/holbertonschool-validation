build: ## Build the website
	@hugo
	@go build -o awesome-api

clean: ## Clean the dist folder
	@pkill awesome-api
	@rm -rf awesome-api awesome-api.log

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

test: ## Test on certain space
	@curl http://localhost:9999
	@curl http://localhost:9999/health