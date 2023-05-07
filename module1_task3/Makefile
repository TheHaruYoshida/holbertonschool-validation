build: ## Build the website
	@hugo

clean: ## Clean the dist folder
	@rm -rf dist

post: ## Create a new blog post
	@hugo new posts/$(POST_NAME).md
	@echo "---\
	title: '$(POST_TITLE)'\
	date: $(date +"%Y-%m-%dT%H:%M:%S%z")\
	---" > content/posts/$(POST_NAME).md

help: ## Display the help command list
	@sed -ne '/@sed/!s/## //p' ${MAKEFILE_LIST}