# Website Build and Lifecycle Instructions

This document provides instructions on how to build and manage the Go-Hugo website, including the requirements and lifecycle.
The website should adhere to the following requirements:

## Prerequisites

-A Valid Go-Hugo website is provided

-There are no Git Submodules

-The theme ananke is installed

-No directory dist/ committed

-Makefile present

## Lifecycle

-“build”: This command will run the Hugo static site generator to generate the website's static files.

-“clean”: This command will remove the "dist/" directory, ensuring a clean state for future builds.

-“post”: This command will create a new blog post.

-“help”: This command will display the help command list.