# Certonaut Documentation

[![ci](https://github.com/certonaut/docs/actions/workflows/ci.yml/badge.svg)](https://github.com/certonaut/docs/actions/workflows/ci.yml)
[![pages-build-deployment](https://github.com/certonaut/docs/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/certonaut/docs/actions/workflows/pages/pages-build-deployment)

This repo contains certonaut's online markdown documentation. To view the documentation online, go to https://docs.certonaut.net

## Contributing

Contributions are highly welcome!

* For simple changes, you may want to consider pressing the "edit file" button on the GitHub web ui. This will guide you through the steps to fork this repository and make a pull request.
* For more complex changes, you will likely want to:
  1. Fork this repository
  2. Download it to your computer by git-"cloning" it
  3. Installing [Material for mkdocs](https://github.com/squidfunk/mkdocs-material). Follow their [installation instructions](https://squidfunk.github.io/mkdocs-material/getting-started/#installation) to do so (probably boils down to a `pip install mkdocs-material`, or docker).
  4. From within the repositories root directory, run `mkdocs serve` to spin up a development webserver. This server will show you any changes you make (almost) live. Note the URL from the `mkdocs serve` command, usually `http://127.0.0.1:8000/`.
  5. Once you're satisfied with your changes, commit them and submit them as a pull request against this repository. Target the `main` branch.
